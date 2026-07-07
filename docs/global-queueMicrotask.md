---
id: global-queueMicrotask
title: queueMicrotask
---

The global [`queueMicrotask`](https://developer.mozilla.org/en-US/docs/Web/API/Window/queueMicrotask) function, as defined in Web specifications. It queues a function to be executed as a microtask, i.e. after the currently executing task finishes and before control returns to the event loop.

---

# Reference

## Methods

### `queueMicrotask()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/queueMicrotask).

Queues a microtask to be executed at a safe time prior to control returning to the event loop. Microtasks run after the current synchronous work completes but before any timers or rendering, making them useful for ordering work that should happen "right after" the current task without yielding to other tasks.

```ts
queueMicrotask(callback): void
```

#### Parameters

**`callback`**

A function to be executed when the JavaScript engine determines it is safe to run queued microtasks. If the callback throws, the exception is reported without interrupting the execution of other microtasks.

Calling `queueMicrotask()` with no arguments, or with an argument that is not a function, throws a `TypeError`.
