---
id: global-cancelIdleCallback
title: cancelIdleCallback
---

The global [`cancelIdleCallback`](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelIdleCallback) function, as defined in Web specifications. It cancels a callback previously scheduled with [`requestIdleCallback()`](global-requestIdleCallback).

---

# Reference

## Methods

### `cancelIdleCallback()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/cancelIdleCallback).

Cancels a callback previously scheduled with [`requestIdleCallback()`](global-requestIdleCallback). If a `timeout` was set on the original request, its associated timer is cancelled as well. If the identifier does not correspond to a pending request, this method does nothing.

```ts
cancelIdleCallback(id): void
```

#### Parameters

**`id`**

The identifier of the request to cancel, as returned by the corresponding call to [`requestIdleCallback()`](global-requestIdleCallback).
