---
name: debugging-issues
description: Debugs errors, test failures, and unexpected behavior. Use when encountering errors, analyzing stack traces, or investigating bugs. Triggers on "debug", "error", "not working", "fails", "broken".
---

# Debugging Specialist

Expert debugger for root cause analysis in BookInk (Next.js 16, TypeScript, Supabase).

## Workflow

### 1. Capture the Error

```bash
# Check terminal for errors
# Check browser console
# Check Supabase logs
```

Use Supabase MCP for backend logs:
```
mcp__supabase__get_logs service: "api"
mcp__supabase__get_logs service: "postgres"
mcp__supabase__get_logs service: "auth"
```

### 2. Gather Context

- Exact error message and stack trace
- Steps to reproduce
- Recent code changes (`git diff`, `git log -5`)
- Environment (dev/prod, browser)

### 3. Isolate the Problem

```bash
# Find error origin
grep -r "ErrorMessage" --include="*.ts" --include="*.tsx"

# Check recent changes to affected file
git log -5 --oneline -- path/to/file.ts

# See what changed
git diff HEAD~3 -- path/to/file.ts
```

### 4. Form Hypotheses

Common causes in BookInk:

| Symptom | Likely Cause |
|---------|--------------|
| "Cannot read properties of undefined" | Missing null check, async timing |
| "Hydration mismatch" | Server/client render difference |
| "Failed to fetch" | API route error, CORS, network |
| "RLS policy violation" | Missing or wrong RLS policy |
| "Invalid hook call" | Hook in server component or conditional |
| "Module not found" | Wrong import path, missing dep |

### 5. Debug Strategically

```typescript
// Add targeted logging
console.log('[DEBUG] Variable state:', { 
  shopId, 
  userId: user?.id,
  timestamp: new Date().toISOString()
})

// For API routes
export async function POST(request: Request) {
  console.log('[API] Request received')
  try {
    const body = await request.json()
    console.log('[API] Body:', body)
    // ... logic
  } catch (error) {
    console.error('[API] Error:', error)
    throw error
  }
}
```

### 6. Implement Fix

Minimal, targeted changes:
```typescript
// ❌ Rewriting entire function
// ✅ Fix the specific issue

// Before
const name = user.profile.name

// After (null-safe)
const name = user?.profile?.name ?? 'Unknown'
```

### 7. Verify Solution

```bash
# Run the app
bun dev

# Run tests if available
bun test

# Check types
bun tsc --noEmit

# Check lint
bun lint
```

## Common BookInk Debugging Scenarios

### Supabase Query Errors

```typescript
// Check the query result
const { data, error } = await supabase
  .from('bookings')
  .select('*')
  .eq('shop_id', shopId)

if (error) {
  console.error('Supabase error:', {
    message: error.message,
    code: error.code,
    details: error.details,
    hint: error.hint
  })
}
```

### Auth Issues

```typescript
// Verify user session
const { data: { user }, error } = await supabase.auth.getUser()
console.log('Auth state:', { 
  hasUser: !!user, 
  userId: user?.id,
  error: error?.message 
})
```

### Server Component Errors

```typescript
// Server components can't use:
// - useState, useEffect, useContext
// - onClick, onChange handlers
// - browser APIs (window, document)

// Check if 'use client' is needed
```

### API Route Debugging

```typescript
// 1. Log incoming request
export async function POST(request: Request) {
  const url = new URL(request.url)
  console.log('[Route]', request.method, url.pathname)
  
  // 2. Validate input
  const body = await request.json()
  if (!body.shopId) {
    return Response.json({ error: 'Missing shopId' }, { status: 400 })
  }
  
  // 3. Track database operations
  const { data, error } = await supabase.from('shops').select()
  console.log('[DB] Result:', { count: data?.length, error })
}
```

## Output Format

```markdown
# Debug Report: [Issue Title]

## Error
```
[Exact error message and stack trace]
```

## Root Cause
[Clear explanation of why this happened]

## Evidence
- [What you found that confirms the diagnosis]
- [Relevant log output or code behavior]

## Fix
```typescript
// [Specific code change]
```

## Verification
- [ ] Error no longer occurs
- [ ] Related functionality still works
- [ ] No new TypeScript/lint errors

## Prevention
[How to avoid this issue in the future]
```

## Quick Diagnostics

```bash
# TypeScript errors
bun tsc --noEmit 2>&1 | head -50

# Build errors
bun run build 2>&1 | grep -A 5 "Error"

# Check if dev server is running
curl -I http://localhost:3000

# Database connectivity
# Use mcp__supabase__execute_sql with: SELECT 1
```
