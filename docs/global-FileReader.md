---
id: global-FileReader
title: FileReader
---

The global [`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader) class, as defined in Web specifications. It lets you asynchronously read the contents of a [`Blob`](global-Blob) or [`File`](global-File) into memory.

`FileReader` extends [`EventTarget`](global-EventTarget), and reports progress and completion by dispatching events and via the corresponding `on*` event handler properties.

:::warning[Partial support]
React Native's `FileReader` does not implement the standard `readAsBinaryString()` method. Reads always resolve asynchronously; the `loadstart` and `progress` events are not dispatched, so the `onloadstart` and `onprogress` handlers are never invoked even though they exist.
:::

---

# Reference

## Constructor

### `FileReader()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/FileReader).

Creates a new `FileReader` object.

```ts
new FileReader();
```

## Static properties

### `EMPTY`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState).

The constant value `0`. No data has been loaded yet.

### `LOADING`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState).

The constant value `1`. Data is currently being loaded.

### `DONE`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState).

The constant value `2`. The entire read request has completed.

## Instance properties

The `EMPTY`, `LOADING`, and `DONE` constants are also available as instance properties, matching the static properties above.

### `error`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error).

An error representing the reason why the read operation failed, or `null` if there was no error.

### `readyState`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState).

A number indicating the state of the `FileReader`. This is one of `EMPTY`, `LOADING`, or `DONE`.

### `result`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/result).

The file's contents. This is `null` at first and is populated once the read completes; its type depends on which read method was used. It is a string for `readAsText()` and `readAsDataURL()`, and an `ArrayBuffer` for `readAsArrayBuffer()`.

### `onabort`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/abort_event).

An event handler for the `abort` event, fired when a read is aborted.

### `onerror`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error_event).

An event handler for the `error` event, fired when a read fails.

### `onload`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/load_event).

An event handler for the `load` event, fired when a read completes successfully.

### `onloadstart`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/loadstart_event).

An event handler for the `loadstart` event.

:::warning[Partial support]
React Native never dispatches the `loadstart` event, so this handler is not invoked.
:::

### `onloadend`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/loadend_event).

An event handler for the `loadend` event, fired when a read finishes, whether it succeeded or failed.

### `onprogress`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/progress_event).

An event handler for the `progress` event.

:::warning[Partial support]
React Native never dispatches the `progress` event, so this handler is not invoked.
:::

## Instance methods

### `abort()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/abort).

Aborts the read operation. Upon return, the `readyState` is `DONE`.

```ts
abort();
```

### `readAsArrayBuffer()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsArrayBuffer).

Starts reading the contents of the specified blob. When finished, `result` contains an `ArrayBuffer` representing the file's data.

```ts
readAsArrayBuffer(blob);
```

#### Parameters

| Name   | Type                                       | Description                         |
| ------ | ------------------------------------------ | ----------------------------------- |
| `blob` | [Blob](global-Blob) \| [File](global-File) | The blob or file to read. Required. |

### `readAsDataURL()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsDataURL).

Starts reading the contents of the specified blob. When finished, `result` contains a `data:` URL representing the file's data.

```ts
readAsDataURL(blob);
```

#### Parameters

| Name   | Type                                       | Description                         |
| ------ | ------------------------------------------ | ----------------------------------- |
| `blob` | [Blob](global-Blob) \| [File](global-File) | The blob or file to read. Required. |

### `readAsText()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsText).

Starts reading the contents of the specified blob. When finished, `result` contains the file's contents as a text string.

```ts
readAsText(blob, encoding?)
```

#### Parameters

| Name       | Type                                       | Description                                      |
| ---------- | ------------------------------------------ | ------------------------------------------------ |
| `blob`     | [Blob](global-Blob) \| [File](global-File) | The blob or file to read. Required.              |
| `encoding` | string                                     | The text encoding to use. Defaults to `'UTF-8'`. |
