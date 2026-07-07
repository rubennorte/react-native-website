---
id: global-clearInterval
title: clearInterval
---

The global [`clearInterval`](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearInterval) function, as defined in Web specifications. It cancels a repeating action previously established by calling [`setInterval()`](global-setInterval).

---

# Reference

## Methods

### `clearInterval()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearInterval).

Cancels a repeating timer previously created with [`setInterval()`](global-setInterval). If the identifier does not correspond to an active interval, this method does nothing.

```ts
clearInterval(id): void
```

#### Parameters

**`id`**

The identifier of the interval to cancel, as returned by the corresponding call to [`setInterval()`](global-setInterval).
