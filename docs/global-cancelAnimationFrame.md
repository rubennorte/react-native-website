---
id: global-cancelAnimationFrame
title: cancelAnimationFrame
---

The global [`cancelAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame) function, as defined in Web specifications. It cancels an animation frame request previously scheduled with [`requestAnimationFrame()`](global-requestAnimationFrame).

---

# Reference

## Methods

### `cancelAnimationFrame()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelAnimationFrame).

Cancels a callback previously scheduled with [`requestAnimationFrame()`](global-requestAnimationFrame). If the identifier does not correspond to a pending request, this method does nothing.

```ts
cancelAnimationFrame(id): void
```

#### Parameters

**`id`**

The identifier of the request to cancel, as returned by the corresponding call to [`requestAnimationFrame()`](global-requestAnimationFrame).
