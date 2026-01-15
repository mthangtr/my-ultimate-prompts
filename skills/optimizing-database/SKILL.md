---
name: optimizing-database
description: Optimizes PostgreSQL database performance for Supabase. Use when diagnosing slow queries, adding indexes, fixing RLS policies, or running performance audits. Triggers on "optimize database", "slow query", "add index", "RLS performance".
---

# Database Optimization for Supabase PostgreSQL

Specialist skill for optimizing BookInk's Supabase PostgreSQL database. Focuses on measurable performance improvements via Supabase MCP Server.

## Workflow

### 1. Run Performance Audit

Always start by checking current advisors:

```
mcp__supabase__get_advisors type: "performance"
mcp__supabase__get_advisors type: "security"
```

### 2. Analyze Schema

```
mcp__supabase__list_tables schemas: ["public"]
mcp__supabase__list_migrations
```

### 3. Execute Diagnostic Queries

Use `mcp__supabase__execute_sql` for analysis:

```sql
-- Check table sizes
SELECT schemaname, tablename, 
       pg_size_pretty(pg_total_relation_size(schemaname || '.' || tablename)) as size
FROM pg_tables 
WHERE schemaname = 'public'
ORDER BY pg_total_relation_size(schemaname || '.' || tablename) DESC;

-- List all indexes
SELECT tablename, indexname, indexdef
FROM pg_indexes
WHERE schemaname = 'public'
ORDER BY tablename, indexname;

-- Find missing indexes on FKs
SELECT
    tc.table_name,
    kcu.column_name,
    ccu.table_name AS foreign_table_name
FROM information_schema.table_constraints tc
JOIN information_schema.key_column_usage kcu 
    ON tc.constraint_name = kcu.constraint_name
JOIN information_schema.constraint_column_usage ccu 
    ON ccu.constraint_name = tc.constraint_name
WHERE tc.constraint_type = 'FOREIGN KEY'
AND tc.table_schema = 'public';
```

### 4. Apply Fixes via Migration

Use `mcp__supabase__apply_migration` for DDL changes:

```sql
-- Example: Add missing FK index
CREATE INDEX CONCURRENTLY idx_bookings_service_id 
ON public.bookings(service_id);
```

## Known Issues in BookInk Database

### Priority 1: Unindexed Foreign Keys (INFO)
- `bookings.service_id` → Add index
- `notifications.booking_id` → Add index

### Priority 2: RLS auth.* Performance (WARN)
All RLS policies use `auth.uid()` directly instead of `(select auth.uid())`, causing re-evaluation per row.

**Fix pattern:**
```sql
-- Bad: auth.uid() called per row
CREATE POLICY "example" ON table
USING (user_id = auth.uid());

-- Good: auth.uid() called once via subquery
CREATE POLICY "example" ON table
USING (user_id = (select auth.uid()));
```

Affected tables: shops, services, portfolio_images, review_images, bookings, blocked_times, notification_logs, notifications, reviews

### Priority 3: Multiple Permissive Policies (WARN)
Tables with redundant SELECT policies:
- `bookings`: "Anyone can view bookings" + "Shop owners can view their bookings"
- `portfolio_images`: Public view + Owner view
- `review_images`: Public view + Owner view
- `reviews`: Public view + Owner view
- `services`: Active services view + Owner view

**Fix:** Combine into single policy with OR condition.

### Priority 4: Unused Indexes (INFO)
- `idx_notification_logs_booking`
- `notifications_is_read_idx`
- `notifications_created_at_idx`

Review and remove if truly unused after monitoring.

## Index Strategy for BookInk

### High-Value Indexes (Add if Missing)

```sql
-- Bookings queries (most frequent)
CREATE INDEX idx_bookings_shop_date ON bookings(shop_id, booking_date);
CREATE INDEX idx_bookings_status ON bookings(status) WHERE status IN ('pending', 'confirmed');

-- Services lookup
CREATE INDEX idx_services_shop_active ON services(shop_id) WHERE is_active = true;

-- Reviews for public profile
CREATE INDEX idx_reviews_shop_visible ON reviews(shop_id) WHERE is_visible = true;

-- Notifications (unread first)
CREATE INDEX idx_notifications_shop_unread ON notifications(shop_id, created_at DESC) WHERE is_read = false;
```

### Index Guidelines
1. Use partial indexes for filtered queries
2. Include frequently filtered columns in compound indexes
3. Put high-cardinality columns first
4. Use CONCURRENTLY to avoid locks

## RLS Policy Optimization Template

```sql
-- Drop old policy
DROP POLICY IF EXISTS "Old policy name" ON table_name;

-- Create optimized policy with subquery wrapper
CREATE POLICY "New policy name" ON table_name
FOR SELECT USING (
    shop_id IN (
        SELECT id FROM shops WHERE user_id = (select auth.uid())
    )
);
```

## Query Optimization Checklist

1. **EXPLAIN ANALYZE** before optimizing
2. Check for sequential scans on large tables
3. Look for nested loops that could use indexes
4. Identify N+1 query patterns in API routes
5. Consider materialized views for complex aggregations

## Monitoring Queries

```sql
-- Slow queries (if pg_stat_statements enabled)
SELECT query, calls, mean_exec_time, total_exec_time
FROM pg_stat_statements
ORDER BY mean_exec_time DESC
LIMIT 10;

-- Table bloat estimate
SELECT schemaname, tablename,
       pg_size_pretty(pg_table_size(schemaname || '.' || tablename)) as table_size,
       n_dead_tup as dead_tuples
FROM pg_stat_user_tables
WHERE n_dead_tup > 1000
ORDER BY n_dead_tup DESC;

-- Index usage stats
SELECT schemaname, tablename, indexname, idx_scan, idx_tup_read
FROM pg_stat_user_indexes
WHERE schemaname = 'public'
ORDER BY idx_scan;
```

## Output Requirements

When optimizing, provide:
1. Current issue (from advisors or analysis)
2. Proposed migration SQL
3. Expected performance impact
4. Verification query to confirm fix
