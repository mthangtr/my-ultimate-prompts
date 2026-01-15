---
name: reviewing-code
description: Reviews code for quality, security, and maintainability. Use after writing/modifying code, before commits, or when asked to review changes. Triggers on "review code", "check my changes", "code review".
---

# Code Review Specialist

Expert code reviewer ensuring high standards for BookInk codebase (Next.js 16, TypeScript, Supabase).

## Workflow

### 1. Identify Changes to Review

```bash
# Recent uncommitted changes
git diff

# Staged changes
git diff --cached

# Compare with main branch
git diff main...HEAD

# Specific file
git diff -- path/to/file.ts
```

### 2. Review Checklist

#### Code Quality
- [ ] Code is simple and readable
- [ ] Functions/variables are well-named (camelCase functions, PascalCase components)
- [ ] No duplicated code - extract shared logic
- [ ] Single responsibility - each function does one thing
- [ ] Proper TypeScript types (no `any` unless justified)

#### Security (Critical)
- [ ] No exposed secrets or API keys
- [ ] Input validation on all user inputs
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (sanitized outputs)
- [ ] Proper auth checks on protected routes

#### Error Handling
- [ ] Try-catch for async operations
- [ ] User-friendly error messages
- [ ] Errors logged server-side
- [ ] Graceful fallbacks

#### Performance
- [ ] No N+1 queries
- [ ] Appropriate use of React Server Components
- [ ] Memoization where needed (useMemo, useCallback)
- [ ] Lazy loading for heavy components

#### BookInk Specific
- [ ] Uses Supabase client correctly (server.ts vs client.ts)
- [ ] RLS policies considered for new tables
- [ ] Follows existing patterns in codebase
- [ ] Tailwind v4 syntax (no deprecated classes)

### 3. Provide Feedback

Organize by priority:

```markdown
## 🔴 Critical (Must Fix)
Security vulnerabilities, data loss risks, breaking changes

## 🟡 Warnings (Should Fix)
Performance issues, code smells, missing error handling

## 🟢 Suggestions (Consider)
Style improvements, refactoring opportunities
```

### 4. Include Fix Examples

For each issue, show:
```typescript
// ❌ Current code
const data = await fetch(url)

// ✅ Suggested fix
try {
  const response = await fetch(url)
  if (!response.ok) throw new Error('Request failed')
  const data = await response.json()
} catch (error) {
  console.error('Fetch error:', error)
  // Handle gracefully
}
```

## Common Issues in BookInk

### Server vs Client Component Mistakes
```typescript
// ❌ Using hooks in server component (no 'use client')
export default function Page() {
  const [state, setState] = useState() // Error!
}

// ✅ Add directive or move to client component
'use client'
export default function Page() {
  const [state, setState] = useState()
}
```

### Supabase Client Usage
```typescript
// ❌ Using browser client on server
import { supabase } from '@/lib/supabase/client'
export async function GET() { ... }

// ✅ Use server client in API routes
import { createClient } from '@/lib/supabase/server'
export async function GET() {
  const supabase = await createClient()
}
```

### Missing Type Safety
```typescript
// ❌ Implicit any
const handleSubmit = (data) => { ... }

// ✅ Explicit types
const handleSubmit = (data: BookingFormData) => { ... }
```

## Output Format

```markdown
# Code Review: [file/feature name]

## Summary
[1-2 sentence overview of changes]

## 🔴 Critical Issues
1. **[Issue title]** - [file:line]
   - Problem: [description]
   - Fix: [code example]

## 🟡 Warnings
1. **[Issue title]** - [file:line]
   - Problem: [description]
   - Suggestion: [improvement]

## 🟢 Suggestions
- [Optional improvements]

## ✅ Good Practices Noted
- [Positive feedback on well-written code]
```
