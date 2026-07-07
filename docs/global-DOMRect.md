---
id: global-DOMRect
title: DOMRect
---

The global [`DOMRect`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect) interface, as defined in Web specifications. It describes the size and position of a rectangle.

`DOMRect` extends [`DOMRectReadOnly`](global-DOMRectReadOnly), adding writable properties. It is the type returned by APIs such as [`getBoundingClientRect()`](element-nodes).

---

# Reference

## Constructor

### `DOMRect()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/DOMRect).

Creates a new `DOMRect` object.

```ts
new DOMRect(x?, y?, width?, height?)
```

#### Parameters

| Name     | Type   | Description                                      |
| -------- | ------ | ------------------------------------------------ |
| `x`      | number | The x coordinate of the origin. Defaults to `0`. |
| `y`      | number | The y coordinate of the origin. Defaults to `0`. |
| `width`  | number | The width of the rectangle. Defaults to `0`.     |
| `height` | number | The height of the rectangle. Defaults to `0`.    |

## Static methods

### `fromRect()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/fromRect_static).

Creates a new `DOMRect` object with a given location and dimensions.

```ts
static fromRect(rectangle?)
```

## Instance properties

_In addition to the properties inherited from [`DOMRectReadOnly`](global-DOMRectReadOnly), the following properties are writable._

### `x`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/x).

The x coordinate of the `DOMRect`'s origin.

### `y`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/y).

The y coordinate of the `DOMRect`'s origin.

### `width`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/width).

The width of the `DOMRect`.

### `height`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRect/height).

The height of the `DOMRect`.
