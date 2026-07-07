---
id: global-AbortController
title: AbortController
---

The global [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController) class, as defined in Web specifications. It represents a controller object that allows you to abort one or more asynchronous operations as and when desired.

An `AbortController` exposes an associated [`AbortSignal`](global-AbortSignal), which can be passed to abortable operations (such as `fetch` or [`EventTarget.addEventListener()`](global-EventTarget#addeventlistener)) to signal cancellation.

---

# Reference

## Constructor

### `AbortController()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/AbortController).

Creates a new `AbortController` object instance.

```ts
new AbortController();
```

## Instance properties

### `signal`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/signal).

Returns the [`AbortSignal`](global-AbortSignal) object associated with this object.

```ts
get signal(): AbortSignal;
```

## Instance methods

### `abort()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortController/abort).

Aborts an asynchronous operation before it has completed. This is able to abort [fetch requests](network), consumption of any response bodies, and streams. It signals to any observers of the associated [`signal`](#signal) that the associated activity is to be aborted.

```ts
abort(reason?): void
```

#### Parameters

**`reason`** (optional)

The reason why the operation was aborted, which can be any JavaScript value. If not specified, the reason is set to an `"AbortError"` [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).
