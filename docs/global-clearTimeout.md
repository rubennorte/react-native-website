---
id: global-clearTimeout
title: clearTimeout
---

The global [`clearTimeout`](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearTimeout) function, as defined in Web specifications. It cancels a timeout previously established by calling [`setTimeout()`](global-setTimeout).

---

# Reference

## Methods

### `clearTimeout()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearTimeout).

Cancels a timer previously created with [`setTimeout()`](global-setTimeout). If the identifier does not correspond to an active timer, this method does nothing.

```ts
clearTimeout(id): void
```

#### Parameters

**`id`**

The identifier of the timer to cancel, as returned by the corresponding call to [`setTimeout()`](global-setTimeout).
