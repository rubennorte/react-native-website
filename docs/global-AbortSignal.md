---
id: global-AbortSignal
title: AbortSignal
---

The global [`AbortSignal`](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal) class, as defined in Web specifications. It represents a signal object that allows you to communicate with an asynchronous operation (such as a fetch request) and abort it if required, via an [`AbortController`](global-AbortController) object.

`AbortSignal` extends [`EventTarget`](global-EventTarget), so it can dispatch an `abort` event and register listeners for it.

An `AbortSignal` instance cannot be constructed directly. Get one from an [`AbortController`](global-AbortController) via its [`signal`](global-AbortController#signal) property, or create one using the static methods below.

---

# Reference

## Static methods

### `AbortSignal.abort()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort_static).

Returns an `AbortSignal` instance that is already set to aborted.

```ts
static abort(reason?): AbortSignal
```

#### Parameters

**`reason`** (optional)

The reason for the abort, which can be any JavaScript value. If not specified, the reason is set to an `"AbortError"` [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException).

### `AbortSignal.any()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/any_static).

Returns an `AbortSignal` that aborts when any of the given abort signals abort.

```ts
static any(signals): AbortSignal
```

#### Parameters

**`signals`**

An array of `AbortSignal` objects to observe. The returned signal aborts as soon as any of them aborts, adopting its abort reason. If one of the given signals is already aborted, the returned signal is aborted immediately.

### `AbortSignal.timeout()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/timeout_static).

Returns an `AbortSignal` that automatically aborts after a specified time.

```ts
static timeout(time): AbortSignal
```

#### Parameters

**`time`**

The number of milliseconds to wait before aborting. When the time elapses, the signal aborts with a `"TimeoutError"` [`DOMException`](https://developer.mozilla.org/en-US/docs/Web/API/DOMException). Must be a non-negative number.

## Instance properties

### `aborted`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/aborted).

A boolean that is `true` if the associated [`AbortController`](global-AbortController) has signaled to abort, and `false` otherwise.

```ts
get aborted(): boolean;
```

### `reason`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/reason).

A JavaScript value providing the abort reason once the signal has aborted, or `undefined` if the signal has not been aborted.

```ts
get reason(): unknown;
```

### `onabort`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/abort_event).

An event handler property invoked when the signal's `abort` event is fired, that is when the associated asynchronous operation is aborted.

```ts
get onabort(): EventCallback | null;
set onabort(listener: ?EventCallback): void;
```

## Instance methods

### `throwIfAborted()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal/throwIfAborted).

Throws the signal's abort [`reason`](#reason) if the signal has been aborted; otherwise it does nothing.

```ts
throwIfAborted(): void
```

`AbortSignal` also inherits the instance methods of [`EventTarget`](global-EventTarget), including [`addEventListener()`](global-EventTarget#addeventlistener) and [`removeEventListener()`](global-EventTarget#removeeventlistener), which can be used to listen for the `abort` event.
