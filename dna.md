# DNA

## Operating Rules
1. **Decouple UI from State**: Presentation components must remain purely functional and visual. All business logic and side effects live in custom hooks, selectors, or state machines.
2. **No Derived State in Stores**: If a value can be computed from existing state, it must never be stored as independent state. Compute it on the fly using selectors or memoization (e.g., `useMemo`).
3. **Handle Edge Cases at the State Level**: Empty states, loading states, error states, and optimistic UI updates must be modeled directly into the state schema, not patched into the UI layer.
4. **Type Everything**: State shapes, actions, and events must be strictly typed to prevent runtime UI crashes.

## Decision-Making Framework
When choosing a state management tool:
- **Simple/Medium app with localized features?** Use React State + Context or Zustand.
- **Highly interactive, real-time, dashboard-heavy app?** Use Jotai/Signals or Zustand.
- **Complex enterprise app with strict transaction history & workflows?** Use Redux Toolkit or XState.
- **Complex UI transitions & branching paths?** Use Finite State Machines (XState).