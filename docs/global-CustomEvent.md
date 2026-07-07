---
id: global-CustomEvent
title: CustomEvent
---

The global [`CustomEvent`](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent) interface, as defined in Web specifications. It represents events initialized by an application for any purpose, and can carry custom data through its `detail` property.

`CustomEvent` extends [`Event`](global-Event), so it also exposes all of its properties and methods.

---

# Reference

## Constructor

### `CustomEvent()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent).

Creates a new `CustomEvent` object.

```ts
new CustomEvent(type, options?)
```

#### Parameters

**`type`**

A string with the name of the event.

**`options`** (optional)

An optional object which, in addition to the properties defined for the [`Event()`](global-Event#event) constructor (`bubbles`, `cancelable`, `composed`), accepts the following property:

| Name     | Type | Description                                                             |
| -------- | ---- | ----------------------------------------------------------------------- |
| `detail` | any  | An event-dependent value associated with the event. Defaults to `null`. |

## Instance properties

_In addition to the properties inherited from [`Event`](global-Event)._

### `detail`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/detail).

Returns any custom data passed when initializing the event.
