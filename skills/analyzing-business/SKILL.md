---
name: analyzing-business
description: Analyzes business metrics, KPIs, revenue, and growth patterns for BookInk. Use for cohort analysis, unit economics, investor reporting, and data-driven decisions. Triggers on "business metrics", "KPIs", "revenue analysis", "cohort".
---

# Business Analysis for BookInk

Transforms BookInk data into actionable insights for growth decisions.

## BookInk Business Model Context

- **Revenue**: Subscription-based for shop owners
- **Key Entities**: Shops, Bookings, Services, Reviews
- **Growth Metrics**: New shops, booking volume, customer retention

## Quick Metrics Queries

Use `mcp__supabase__execute_sql` for all queries:

### Shop Growth
```sql
SELECT 
    DATE_TRUNC('month', created_at) as month,
    COUNT(*) as new_shops,
    COUNT(*) FILTER (WHERE created_at >= NOW() - INTERVAL '30 days') as last_30d
FROM shops
GROUP BY DATE_TRUNC('month', created_at)
ORDER BY month DESC;
```

### Booking Volume
```sql
SELECT 
    DATE_TRUNC('week', created_at) as week,
    COUNT(*) as total_bookings,
    COUNT(*) FILTER (WHERE status = 'completed') as completed,
    COUNT(*) FILTER (WHERE status = 'cancelled') as cancelled,
    ROUND(COUNT(*) FILTER (WHERE status = 'completed') * 100.0 / NULLIF(COUNT(*), 0), 1) as completion_rate
FROM bookings
GROUP BY DATE_TRUNC('week', created_at)
ORDER BY week DESC
LIMIT 12;
```

### Revenue per Shop (if pricing exists)
```sql
SELECT 
    s.name as shop_name,
    COUNT(b.id) as total_bookings,
    SUM(sv.price) as total_revenue,
    AVG(sv.price) as avg_booking_value
FROM shops s
LEFT JOIN bookings b ON s.id = b.shop_id AND b.status = 'completed'
LEFT JOIN services sv ON b.service_id = sv.id
GROUP BY s.id, s.name
ORDER BY total_revenue DESC NULLS LAST;
```

### Service Popularity
```sql
SELECT 
    sv.name as service_name,
    s.name as shop_name,
    COUNT(b.id) as times_booked,
    sv.price,
    sv.duration_minutes
FROM services sv
JOIN shops s ON sv.shop_id = s.id
LEFT JOIN bookings b ON sv.id = b.service_id
WHERE sv.is_active = true
GROUP BY sv.id, sv.name, s.name, sv.price, sv.duration_minutes
ORDER BY times_booked DESC;
```

## Key Performance Indicators

### For BookInk MVP

| KPI | Query Focus | Target |
|-----|-------------|--------|
| Active Shops | Shops with bookings in last 30 days | Growth |
| Booking Conversion | Completed / Total bookings | >80% |
| Avg Bookings/Shop | Total bookings / Active shops | Engagement |
| Review Rate | Reviews / Completed bookings | >20% |
| Repeat Customers | Customers with 2+ bookings | Retention |

### Cohort Analysis Template
```sql
-- Shop activation cohort
WITH shop_cohorts AS (
    SELECT 
        id as shop_id,
        DATE_TRUNC('month', created_at) as cohort_month
    FROM shops
),
monthly_activity AS (
    SELECT 
        b.shop_id,
        DATE_TRUNC('month', b.created_at) as activity_month
    FROM bookings b
    GROUP BY b.shop_id, DATE_TRUNC('month', b.created_at)
)
SELECT 
    sc.cohort_month,
    COUNT(DISTINCT sc.shop_id) as cohort_size,
    ma.activity_month,
    COUNT(DISTINCT ma.shop_id) as active_shops,
    ROUND(COUNT(DISTINCT ma.shop_id) * 100.0 / COUNT(DISTINCT sc.shop_id), 1) as retention_pct
FROM shop_cohorts sc
LEFT JOIN monthly_activity ma ON sc.shop_id = ma.shop_id
GROUP BY sc.cohort_month, ma.activity_month
ORDER BY sc.cohort_month, ma.activity_month;
```

## Unit Economics (Future)

When monetization is implemented:

```
CAC = Marketing Spend / New Paying Shops
LTV = ARPU * (1 / Monthly Churn Rate)
Payback Period = CAC / Monthly Revenue per Shop
Target: LTV:CAC > 3:1
```

## Report Template

```markdown
# BookInk Business Report - [Date]

## Executive Summary
- Total Shops: X (±Y% vs last month)
- Total Bookings: X (±Y% vs last month)
- Completion Rate: X%

## Growth Metrics
| Metric | This Month | Last Month | Change |
|--------|------------|------------|--------|
| New Shops | X | Y | ±Z% |
| Bookings | X | Y | ±Z% |
| Active Shops | X | Y | ±Z% |

## Top Performing Shops
[Table of shops by booking volume]

## Insights & Recommendations
1. [Key insight with supporting data]
2. [Actionable recommendation]
```

## Alert Thresholds

Monitor and flag:
- Weekly bookings drop >20%
- Cancellation rate >25%
- New shop signups stall
- Average bookings per shop declining
