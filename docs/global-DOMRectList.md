---
id: global-DOMRectList
title: DOMRectList
---

The global [`DOMRectList`](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectList) interface, as defined in Web specifications. It represents a collection of [`DOMRect`](global-DOMRect) objects, typically returned by APIs that produce a list of rectangles.

`DOMRectList` is iterable, so it can be used with `for...of` loops and the spread operator.

---

# Reference

## Instance properties

### `length`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectList/length).

Returns the number of `DOMRect` objects in the list.

## Instance methods

### `item()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/DOMRectList/item).

Returns the `DOMRect` at the given index, or `null` if the index is out of range.

```ts
item(index);
```
