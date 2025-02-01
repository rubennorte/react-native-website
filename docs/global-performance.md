---
id: global-performance
title: performance
---

The global `performance` object provides access to performance-related properties and methods.

This is the same API defined in Web specifications.

### Properties

- `eventCounts`
- `memory`
- `rnStartupTiming` (React Native specific extension)

### Methods

- `clearMarks()`
- `clearMeasures()`
- `getEntries()`
- `getEntriesByName()`
- `getEntriesByType()`
- `mark()`
- `measure()`
- `now()`

---

## Example

```ts
const start = performance.now();

doSomething();

const duration = performance.now() - start;

console.log(`doSomething() took ${duration}ms');
```

You can find additional examples of these properties and methods in MDN.
