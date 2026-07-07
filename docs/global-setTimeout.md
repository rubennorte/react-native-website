---
id: global-setTimeout
title: setTimeout
---

The global [`setTimeout`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout) function, as defined in Web specifications. It schedules a function to be executed after a given delay (in milliseconds).

---

# Reference

## Methods

### `setTimeout()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout).

Sets a timer which executes a function once the timer expires.

```ts
setTimeout(callback, delay?, ...args): number
```

#### Parameters

**`callback`**

A function to be executed after the timer expires.

**`delay`** (optional)

The time, in milliseconds, that the timer should wait before the specified function is executed. If omitted or falsy, a value of `0` is used, meaning the callback runs as soon as possible.

**`...args`** (optional)

Additional arguments which are passed through to the `callback` when the timer expires.

#### Returns

A positive number (the timer identifier) that can be passed to [`clearTimeout()`](global-clearTimeout) to cancel the timer.
