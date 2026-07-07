---
id: global-EventTarget
title: EventTarget
---

The global [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget) interface, as defined in Web specifications. It is implemented by objects that can receive events and may have listeners for them.

Several React Native objects implement `EventTarget`, such as the [DOM nodes](element-nodes) provided by component refs.

---

# Reference

## Constructor

### `EventTarget()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/EventTarget).

Creates a new `EventTarget` object.

```ts
new EventTarget();
```

## Instance methods

### `addEventListener()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener).

Registers an event handler of a specific event type on the `EventTarget`.

```ts
addEventListener(type, callback, options?)
```

#### Parameters

**`type`**

A string representing the event type to listen for.

**`callback`**

The object that receives a notification when an event of the specified type occurs. This must be a function or an object with a `handleEvent()` method.

**`options`** (optional)

A boolean (equivalent to `{capture: boolean}`) or an object with the following properties:

| Name      | Type                              | Description                                                                                                                                               |
| --------- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `capture` | boolean                           | Whether events of this type will be dispatched to this listener before being dispatched to any `EventTarget` beneath it in the tree. Defaults to `false`. |
| `once`    | boolean                           | Whether the listener should be invoked at most once. If `true`, the listener is automatically removed when invoked. Defaults to `false`.                  |
| `passive` | boolean                           | If `true`, indicates that the listener will never call `preventDefault()`. Defaults to `false`.                                                           |
| `signal`  | [AbortSignal](global-AbortSignal) | An `AbortSignal`. The listener is removed when the given signal's `abort()` method is called.                                                             |

### `removeEventListener()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener).

Removes an event listener previously registered with `addEventListener()` from the `EventTarget`.

```ts
removeEventListener(type, callback, options?)
```

### `dispatchEvent()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent).

Dispatches an [`Event`](global-Event) to this `EventTarget`, invoking the affected listeners in the appropriate order. Returns `false` if the event is cancelable and at least one of the event handlers called `preventDefault()`, otherwise `true`.

```ts
dispatchEvent(event);
```
