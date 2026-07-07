---
id: global-Response
title: Response
---

The global [`Response`](https://developer.mozilla.org/en-US/docs/Web/API/Response) class, as defined in Web specifications. It represents the response to a request, and is the type of value that the promise returned by [`fetch`](global-fetch) resolves to.

In React Native, `Response` is provided by the [`whatwg-fetch`](https://github.com/github/fetch) polyfill and is used together with [`fetch`](global-fetch), [`Headers`](global-Headers) and [`Request`](global-Request).

---

# Reference

## Constructor

### `Response()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/Response).

Creates a new `Response` object.

```ts
new Response(body?, options?)
```

#### Parameters

**`body`** (optional)

The body of the response. Can be a string, [`Blob`](global-Blob), `FormData`, `ArrayBuffer`, `ArrayBufferView`, `URLSearchParams`, or `null` (the default).

**`options`** (optional)

An optional object with the following properties:

| Name         | Type                                | Description                                          |
| ------------ | ----------------------------------- | ---------------------------------------------------- |
| `status`     | number                              | The status code for the response. Defaults to `200`. |
| `statusText` | string                              | The status message associated with the status code.  |
| `headers`    | [Headers](global-Headers) \| object | Any headers to add to the response.                  |

## Static methods

### `error()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/error_static).

Returns a new `Response` object associated with a network error.

### `redirect()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/redirect_static).

Returns a new `Response` object that redirects to the specified URL.

## Instance properties

### `status`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/status).

The HTTP status code of the response (e.g. `200` for success).

### `statusText`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/statusText).

The status message corresponding to the status code (e.g. `"OK"` for `200`).

### `ok`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/ok).

A boolean indicating whether the response was successful (status in the range `200`–`299`).

### `headers`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/headers).

The [`Headers`](global-Headers) object associated with the response.

### `url`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/url).

The URL of the response.

### `type`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/type).

The type of the response (e.g. `"default"`, `"error"`).

### `bodyUsed`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/bodyUsed).

A boolean indicating whether the body has already been read.

## Instance methods

### `clone()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/clone).

Creates a copy of the current `Response` object.

### `arrayBuffer()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/arrayBuffer).

Returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representation of the response body.

### `blob()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/blob).

Returns a promise that resolves with a [`Blob`](global-Blob) representation of the response body.

### `formData()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/formData).

Returns a promise that resolves with a `FormData` representation of the response body.

### `json()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/json).

Returns a promise that resolves with the result of parsing the response body as JSON.

### `text()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response/text).

Returns a promise that resolves with a string representation of the response body.

:::warning[Partial support]

Because `Response` is provided by the `whatwg-fetch` polyfill running on top of [`XMLHttpRequest`](global-XMLHttpRequest), some standard members behave differently or are unavailable:

- **No streaming bodies.** `ReadableStream` is not supported, so the `body` property is not available. Read the full body with [`text()`](#text), [`json()`](#json), [`blob()`](#blob) or [`arrayBuffer()`](#arraybuffer) instead.
- **`url` may be unreliable after redirects**, unless the server sets an `X-Request-URL` response header.

For anything not covered here, refer to the [`whatwg-fetch` documentation](https://github.com/github/fetch) and the [`Response` documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Response).

:::
