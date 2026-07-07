---
id: global-fetch
title: fetch
---

The global [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Window/fetch) function, as defined in Web specifications. It starts the process of fetching a resource from the network, returning a promise that is fulfilled once the response is available.

In React Native, `fetch` (together with [`Headers`](global-Headers), [`Request`](global-Request) and [`Response`](global-Response)) is provided by the [`whatwg-fetch`](https://github.com/github/fetch) polyfill, which is implemented on top of [`XMLHttpRequest`](global-XMLHttpRequest). As a result, some parts of the standard Fetch API behave differently or are unavailable (see the note at the end of this page).

---

# Reference

## Call signature

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/fetch).

```ts
fetch(input, init?)
```

### Parameters

**`input`**

The resource to fetch. This can either be:

- A string containing the URL of the resource to fetch, or
- A [`Request`](global-Request) object.

**`init`** (optional)

An object containing options to configure the request. Commonly supported properties include:

| Name          | Type                                                                                           | Description                                                                                                                   |
| ------------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `method`      | string                                                                                         | The request method, e.g. `"GET"` (the default), `"POST"`, `"PUT"`, `"DELETE"`.                                                |
| `headers`     | [Headers](global-Headers) \| object                                                            | Any headers to add to the request, as a [`Headers`](global-Headers) object or an object literal of string values.             |
| `body`        | string \| [Blob](global-Blob) \| FormData \| ArrayBuffer \| ArrayBufferView \| URLSearchParams | The body to send with the request.                                                                                            |
| `credentials` | string                                                                                         | Controls whether cookies are sent with the request. Defaults to `"same-origin"`.                                              |
| `signal`      | [AbortSignal](global-AbortSignal)                                                              | An `AbortSignal` object that allows the request to be aborted via its associated [`AbortController`](global-AbortController). |

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Response`](global-Response) object.

The promise **does not reject on HTTP error statuses** (e.g. `404` or `500`). It only rejects on network failure, or if something prevented the request from completing. Check [`Response.ok`](global-Response#ok) or [`Response.status`](global-Response#status) to detect HTTP errors.

## Example

```ts
const response = await fetch('https://example.com/api/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({key: 'value'}),
});

if (!response.ok) {
  throw new Error(
    `Request failed with status ${response.status}`,
  );
}

const data = await response.json();
```

:::warning[Partial support]

Because `fetch` is provided by the `whatwg-fetch` polyfill running on top of [`XMLHttpRequest`](global-XMLHttpRequest), some parts of the standard Fetch API behave differently or are unavailable:

- **No streaming bodies.** `ReadableStream` is not supported, so responses cannot be streamed and `Response.body` is not available. Use [`Response.text()`](global-Response#text), [`Response.json()`](global-Response#json), [`Response.blob()`](global-Response#blob) or [`Response.arrayBuffer()`](global-Response#arraybuffer) to read the full body instead.
- **The `redirect` and `cache` options are ignored.** Only the default `"follow"` redirect mode is available due to limitations of `XMLHttpRequest`.
- **`keepalive` is not supported.**
- **`response.url` may be unreliable after redirects**, unless the server sets an `X-Request-URL` response header.
- Aborting a request requires [`AbortController`](global-AbortController) and [`AbortSignal`](global-AbortSignal).

For anything not covered here, refer to the [`whatwg-fetch` documentation](https://github.com/github/fetch) and the [Fetch API documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/fetch).

:::
