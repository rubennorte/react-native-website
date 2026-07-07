---
id: global-File
title: File
---

The global [`File`](https://developer.mozilla.org/en-US/docs/Web/API/File) class, as defined in Web specifications. It provides information about files and allows JavaScript to access their contents.

`File` extends [`Blob`](global-Blob), inheriting all of its properties and methods and adding a `name` and a `lastModified` property.

:::warning[Partial support]
Because `File` extends [`Blob`](global-Blob), it shares the same limitations. In particular, the standard `text()`, `arrayBuffer()`, `bytes()`, and `stream()` methods are not implemented. To read the contents of a `File`, use [`FileReader`](global-FileReader) instead.
:::

---

# Reference

## Constructor

### `File()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/File/File).

Creates a new `File` object.

```ts
new File(parts, name, options?)
```

#### Parameters

| Name      | Type                                    | Description                                                                                                    |
| --------- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `parts`   | Array&lt;[Blob](global-Blob) \| string> | An array of `Blob` objects and/or strings that make up the file's contents. Required.                          |
| `name`    | string                                  | A string representing the file name. Required.                                                                 |
| `options` | object                                  | An optional object with a `type` property specifying the MIME type of the data, and a `lastModified` property. |

:::note
Both `parts` and `name` are required. Omitting either argument throws an error.
:::

## Instance properties

_In addition to the properties inherited from [`Blob`](global-Blob) ([`size`](global-Blob#size) and [`type`](global-Blob#type)), `File` provides the following properties._

### `name`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/File/name).

The name of the file represented by the `File` object.

### `lastModified`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/File/lastModified).

The last modified time of the file, in milliseconds since the Unix epoch. Defaults to `0` if not set.

## Instance methods

_`File` inherits the [`slice()`](global-Blob#slice) and `close()` methods from [`Blob`](global-Blob)._
