---
id: global-PerformanceObserver
title: PerformanceObserver
---

The global `PerformanceObserver` class allows observing performance events in the application.

This is the same API defined in Web specifications.

### Constructor

- `constructor()`

### Static properties

- `supportedEntryTypes`

### Instance methods

- `observe()`
- `disconnect()`

---

## Example

```ts
const observer = new PerformanceObserver(
  (list, observer, options) => {
    for (const entry of list.getEntries()) {
      console.log(
        'Received entry with type',
        entry.entryType,
        'and name',
        entry.name,
        'that started at',
        entry.startTime,
        'and took',
        entry.duration,
        'ms',
      );
    }
  },
);

observer.observe({entryTypes: ['mark', 'measure']});
```

You can find additional examples of these properties and methods in MDN.
