---
id: global-setImmediate
title: setImmediate ⚠️
---

:::warning[Non-standard]
`setImmediate` is not part of any Web standard. React Native provides it for compatibility with existing code and libraries (it also exists in [Node.js](https://developer.mozilla.org/en-US/docs/Web/API/Window/setImmediate)). Prefer [`queueMicrotask`](global-queueMicrotask) or [`setTimeout`](global-setTimeout) in new code.
:::

The global `setImmediate` function schedules a callback to be invoked at the end of the current JavaScript execution loop, after the currently executing code completes but before returning control to the event loop.

In React Native, `setImmediate` is implemented on top of [`queueMicrotask`](global-queueMicrotask).

---

# Reference

```ts
setImmediate(callback, ...args);
```

#### Parameters

**`callback`**

The function to call at the end of the current execution loop.

**`...args`** (optional)

Additional arguments which are passed through to the `callback`.

#### Returns

A number, the ID which can be passed to [`clearImmediate()`](global-clearImmediate) to cancel the scheduled callback.
