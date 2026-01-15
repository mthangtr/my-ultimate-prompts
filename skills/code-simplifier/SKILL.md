---
name: code-simplifier
description: Simplifies and refines code for clarity, consistency, and maintainability while preserving functionality. Use when asked to "simplify code", "clean up code", "refactor for readability", or after writing code that needs polish.
---

# Code Simplifier

Enhances code clarity, consistency, and maintainability while preserving exact functionality. Prioritizes readable, explicit code over overly compact solutions.

## Scope

Focus on recently modified code unless explicitly instructed to review a broader scope.

## Refinement Principles

### 1. Preserve Functionality
Never change what the code does - only how it does it. All original features, outputs, and behaviors must remain intact.

### 2. Apply Project Standards
Follow AGENTS.md conventions:
- ES modules with proper import sorting
- `function` keyword over arrow functions
- Explicit return type annotations for top-level functions
- React components with explicit Props types
- Proper error handling (avoid try/catch when possible)
- Consistent naming conventions

### 3. Enhance Clarity
- Reduce unnecessary complexity and nesting
- Eliminate redundant code and abstractions
- Use clear variable and function names
- Consolidate related logic
- Remove comments that describe obvious code
- **Avoid nested ternary operators** - prefer switch statements or if/else chains
- Choose clarity over brevity

### 4. Avoid Over-Simplification
Do not:
- Create overly clever solutions hard to understand
- Combine too many concerns into single functions
- Remove helpful abstractions that improve organization
- Prioritize "fewer lines" over readability (e.g., dense one-liners)
- Make code harder to debug or extend

## Workflow

1. Identify recently modified code sections
2. Analyze for elegance and consistency improvements
3. Apply project-specific best practices
4. Verify functionality remains unchanged
5. Confirm refined code is simpler and more maintainable
6. Document only significant changes affecting understanding
