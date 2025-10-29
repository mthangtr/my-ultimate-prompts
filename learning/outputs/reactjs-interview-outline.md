# DÀN Ý HỌC TẬP: ReactJS cho Phỏng Vấn

## I. Kiến trúc & Cơ chế cốt lõi
### 1.1. React Fundamentals Deep Dive
- Virtual DOM là gì và tại sao cần thiết
- Reconciliation algorithm (Fiber architecture)
- Diffing algorithm hoạt động như thế nào
- Rendering process: từ JSX đến UI
- React Elements vs React Components vs DOM Elements

### 1.2. JSX & Rendering
- JSX transformation process
- React.createElement() dưới hood
- JSX security: XSS protection
- Fragments và tại sao cần thiết
- Key prop và vai trò trong reconciliation

### 1.3. Component Lifecycle (Class & Function)
- Component lifecycle phases
- Mounting, Updating, Unmounting stages
- useEffect vs lifecycle methods mapping
- Cleanup functions và memory leaks
- Effect dependencies array deep dive

### 1.4. State Management Internals
- State batching và automatic batching (React 18)
- setState synchronous vs asynchronous
- State updates và closure traps
- Immutability requirement
- Object.is() comparison trong React

### 1.5. Event System
- Synthetic Events vs Native Events
- Event pooling (legacy behavior)
- Event delegation trong React
- Capturing vs Bubbling phase
- Event handler naming conventions

## II. Hooks Deep Dive
### 2.1. useState Hook
- useState implementation theory
- Lazy initialization
- Functional updates
- Multiple state updates batching
- State với objects và arrays

### 2.2. useEffect Hook
- useEffect execution timing
- Effect dependencies comparison
- Infinite loop scenarios
- Race conditions handling
- Effect cleanup timing

### 2.3. useRef Hook
- useRef vs useState
- DOM manipulation với useRef
- Storing mutable values
- forwardRef và useImperativeHandle
- Callback refs pattern

### 2.4. useMemo & useCallback
- Memoization concepts
- useMemo use cases và pitfalls
- useCallback dependencies
- Premature optimization warnings
- Referential equality problems

### 2.5. useContext Hook
- Context API architecture
- Provider re-render behavior
- Context value memoization
- Multiple contexts composition
- Context vs Redux tradeoffs

### 2.6. useReducer Hook
- useReducer vs useState
- Reducer pattern benefits
- Complex state logic organization
- useReducer với TypeScript
- Middleware pattern simulation

### 2.7. Custom Hooks
- Custom hooks design patterns
- Reusability best practices
- Naming conventions
- Testing custom hooks
- Common custom hooks examples

## III. Performance Optimization
### 3.1. Re-rendering Optimization
- React.memo usage và pitfalls
- PureComponent vs React.memo
- Props comparison strategies
- Children as props pattern
- Component composition for performance

### 3.2. Code Splitting & Lazy Loading
- React.lazy() và dynamic imports
- Suspense component
- Error boundaries với lazy components
- Route-based code splitting
- Bundle size optimization

### 3.3. Profiling & Debugging
- React DevTools Profiler
- Performance metrics interpretation
- Why Did You Render tool
- Console.log pitfalls
- Source maps debugging

### 3.4. Common Performance Pitfalls
- Inline function definitions
- Creating objects/arrays trong render
- Unnecessary context updates
- Large component trees
- N+1 rendering problems

## IV. Advanced Patterns
### 4.1. Composition Patterns
- Children props pattern
- Render props pattern
- Higher-Order Components (HOC)
- Compound components pattern
- Control props pattern

### 4.2. State Management Patterns
- Lifting state up
- State colocation principle
- Prop drilling solutions
- Global state vs Local state
- Server state vs Client state

### 4.3. Error Handling
- Error Boundaries implementation
- getDerivedStateFromError
- componentDidCatch
- Error Boundaries limitations
- Error logging strategies

### 4.4. Refs & DOM Manipulation
- When to use refs
- Callback refs vs useRef
- forwardRef pattern
- useImperativeHandle use cases
- Measuring DOM elements

## V. React 18+ Features
### 5.1. Concurrent Features
- Concurrent rendering concepts
- useTransition hook
- useDeferredValue hook
- startTransition API
- Priority levels trong updates

### 5.2. Suspense & Data Fetching
- Suspense for data fetching
- Streaming SSR
- Suspense boundaries strategies
- Error boundaries với Suspense
- SuspenseList component

### 5.3. Server Components (RSC)
- Server Components vs Client Components
- RSC architecture
- Serialization constraints
- Use cases for Server Components
- Migration strategies

### 5.4. Automatic Batching
- Batching behavior changes
- flushSync API
- Batching trong async code
- Event handlers batching
- React 17 vs React 18 differences

## VI. TypeScript với React
### 6.1. Component Typing
- FC vs function component typing
- Props interface definition
- Children typing options
- Generic components
- Event handler typing

### 6.2. Hooks Typing
- useState type inference
- useRef typing variants
- Custom hooks với generics
- useReducer action typing
- Context typing patterns

### 6.3. Advanced Types
- Discriminated unions
- Utility types (Partial, Pick, Omit)
- React.ComponentProps
- React.ElementType
- ForwardRef typing

## VII. Testing Strategies
### 7.1. Testing Fundamentals
- Testing library philosophy
- Unit vs Integration vs E2E
- Queries priority (getByRole, etc.)
- User-centric testing approach
- Accessibility testing

### 7.2. React Testing Library
- Rendering components
- Querying elements
- Firing events
- Async testing (waitFor, findBy)
- Mocking components và modules

### 7.3. Hooks Testing
- Testing custom hooks
- renderHook utility
- Act warnings understanding
- Testing useEffect
- Testing async hooks

### 7.4. Integration Testing
- Testing component interaction
- User flows testing
- API mocking strategies
- MSW (Mock Service Worker)
- Testing context providers

## VIII. State Management Solutions
### 8.1. Redux Deep Dive
- Redux core concepts
- Redux Toolkit (RTK)
- Slice pattern
- Redux DevTools
- Redux vs Context API

### 8.2. Redux Middleware
- Thunks
- Redux Saga
- Redux Observable
- Custom middleware
- Side effects handling

### 8.3. Alternative Solutions
- Zustand
- Jotai
- Recoil
- MobX
- Comparison matrix

### 8.4. Server State Management
- React Query (TanStack Query)
- SWR
- Apollo Client
- Caching strategies
- Optimistic updates

## IX. Real-world Scenarios
### 9.1. Forms Handling
- Controlled vs Uncontrolled components
- Form libraries (Formik, React Hook Form)
- Validation strategies
- File uploads
- Multi-step forms

### 9.2. Data Fetching Patterns
- useEffect data fetching
- Race conditions prevention
- Abort controller usage
- Polling implementation
- Infinite scrolling

### 9.3. Authentication & Authorization
- Protected routes implementation
- Token management
- Refresh token flow
- Role-based access control
- Auth context pattern

### 9.4. Routing
- React Router v6 features
- Nested routes
- Dynamic routing
- Route guards
- Search params management

## X. Interview-Specific Topics
### 10.1. Common Interview Questions
- Virtual DOM explanation
- Reconciliation detailed explanation
- Keys importance demonstration
- useEffect vs useLayoutEffect
- Controlled vs Uncontrolled inputs

### 10.2. Coding Challenges
- Custom hooks implementation
- Debounce/Throttle hooks
- useLocalStorage hook
- usePrevious hook
- Infinite scroll implementation

### 10.3. System Design với React
- Component architecture design
- State management strategy
- Code organization
- Scalability considerations
- Performance budgets

### 10.4. Best Practices & Patterns
- File structure conventions
- Naming conventions
- Component size guidelines
- When to split components
- Anti-patterns to avoid

### 10.5. Tricky Scenarios
- Stale closure problem
- Race conditions
- Memory leaks identification
- Unnecessary re-renders debugging
- Event handler scope issues
