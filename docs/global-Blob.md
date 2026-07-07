---
id: global-Blob
title: Blob
---

The global [`Blob`](https://developer.mozilla.org/en-US/docs/Web/API/Blob) class, as defined in Web specifications. It represents an opaque reference to some immutable, raw binary data, which in React Native is stored natively.

A `Blob` can be created from other blobs and strings, sliced into new blobs, and referenced from a URL via [`URL.createObjectURL()`](global-URL). It is also produced by other APIs, such as receiving binary messages from a [`WebSocket`](global-WebSocket) with `binaryType` set to `'blob'`.

:::warning[Partial support]
React Native's `Blob` does not implement the standard `text()`, `arrayBuffer()`, `bytes()`, or `stream()` methods. To read the contents of a `Blob`, use [`FileReader`](global-FileReader) instead.
:::

---

# Reference

## Constructor

### `Blob()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Blob/Blob).

Creates a new `Blob` object containing a concatenation of the given parts.

```ts
new Blob(parts?, options?)
```

#### Parameters

| Name      | Type                                    | Description                                                                                                    |
| --------- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `parts`   | Array&lt;[Blob](global-Blob) \| string> | An array of `Blob` objects and/or strings to concatenate into the new blob. Defaults to `[]`.                  |
| `options` | object                                  | An optional object with a `type` property specifying the MIME type of the data, and a `lastModified` property. |

:::warning[Partial support]
React Native only supports creating a `Blob` from other blobs and strings. Other source types accepted by the Web specification (such as `ArrayBuffer` or typed arrays) are not supported.
:::

## Instance properties

### `size`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Blob/size).

The size of the data contained in the `Blob` object, in bytes.

### `type`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Blob/type).

A string indicating the MIME type of the data contained in the `Blob`. If the type is unknown, this string is empty.

## Instance methods

### `slice()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Blob/slice).

Creates and returns a new `Blob` object which contains data from a subset of the blob on which it's called.

```ts
slice(start?, end?, contentType?)
```

#### Parameters

| Name          | Type   | Description                                                                                                                                         |
| ------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| `start`       | number | The index into the blob indicating the first byte to include in the new blob. A negative value is relative to the end of the blob.                  |
| `end`         | number | The index into the blob indicating the first byte that will _not_ be included in the new blob. A negative value is relative to the end of the blob. |
| `contentType` | string | The MIME type of the new blob. Defaults to an empty string.                                                                                         |

:::note
Because `slice()` creates a new view onto the same underlying binary data as the original blob, calling `close()` on any of those views is enough to deallocate the data.
:::

### `close()` ⚠️

:::warning[Non-standard]
This is a React Native specific extension.
:::

Releases the native resources associated with the `Blob`. After a blob has been closed, attempting to access its data throws an error.

```ts
close();
```

React Native cannot deallocate the native binary data backing a `Blob` automatically, so consumers should explicitly call `close()` when a blob is no longer needed to free the underlying resource.

Note that the semantics differ between blobs created via [`slice()`](#slice) and `new Blob([blob])`. `slice()` creates a new _view_ onto the same binary data, so calling `close()` on any of those views is enough to deallocate the data, whereas `new Blob([blob, ...])` copies the data in memory, producing an independent blob.

:::note
This method is defined in the Web specification but is not implemented by browsers. React Native implements it to support explicit deallocation.
:::
