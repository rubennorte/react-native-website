---
id: global-DOMRectReadOnly
title: DOMRectReadOnly
---

The global [`DOMRectReadOnly`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly) interface, as defined in Web specifications. It specifies the standard properties (also used by [`DOMRect`](global-DOMRect)) to define a rectangle whose properties are immutable.

---

# Reference

## Constructor

### `DOMRectReadOnly()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/DOMRectReadOnly).

Creates a new `DOMRectReadOnly` object.

```ts
new DOMRectReadOnly(x?, y?, width?, height?)
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

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/fromRect_static).

Creates a new `DOMRectReadOnly` object with a given location and dimensions.

```ts
static fromRect(rectangle?)
```

## Instance properties

### `x`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/x).

The x coordinate of the `DOMRectReadOnly`'s origin.

### `y`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/y).

The y coordinate of the `DOMRectReadOnly`'s origin.

### `width`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/width).

The width of the `DOMRectReadOnly`.

### `height`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/height).

The height of the `DOMRectReadOnly`.

### `top`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/top).

The top coordinate value of the `DOMRectReadOnly` (has the same value as `y`, or `y + height` if `height` is negative).

### `right`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/right).

The right coordinate value of the `DOMRectReadOnly` (has the same value as `x + width`, or `x` if `width` is negative).

### `bottom`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/bottom).

The bottom coordinate value of the `DOMRectReadOnly` (has the same value as `y + height`, or `y` if `height` is negative).

### `left`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/left).

The left coordinate value of the `DOMRectReadOnly` (has the same value as `x`, or `x + width` if `width` is negative).

## Instance methods

### `toJSON()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectReadOnly/toJSON).

Returns a JSON representation of the `DOMRectReadOnly` object.
