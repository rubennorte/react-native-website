---
id: global-setInterval
title: setInterval
---

The global [`setInterval`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setInterval) function, as defined in Web specifications. It repeatedly executes a function with a fixed time delay (in milliseconds) between each call.

---

# Reference

## Methods

### `setInterval()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/setInterval).

Repeatedly calls a function, with a fixed time delay between each call. The interval keeps running until it is cancelled with [`clearInterval()`](global-clearInterval).

```ts
setInterval(callback, delay?, ...args): number
```

#### Parameters

**`callback`**

A function to be executed every `delay` milliseconds.

**`delay`** (optional)

The time, in milliseconds, that the timer should wait between executions of the specified function. If omitted or falsy, a value of `0` is used.

**`...args`** (optional)

Additional arguments which are passed through to the `callback` on each execution.

#### Returns

A positive number (the interval identifier) that can be passed to [`clearInterval()`](global-clearInterval) to cancel the interval.
