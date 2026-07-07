---
id: global-Request
title: Request
---

The global [`Request`](https://developer.mozilla.org/en-US/docs/Web/API/Request) class, as defined in Web specifications. It represents a resource request, and is typically used together with [`fetch`](global-fetch).

In React Native, `Request` is provided by the [`whatwg-fetch`](https://github.com/github/fetch) polyfill and is used together with [`fetch`](global-fetch), [`Headers`](global-Headers) and [`Response`](global-Response).

---

# Reference

## Constructor

### `Request()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request).

Creates a new `Request` object.

```ts
new Request(input, options?)
```

#### Parameters

**`input`**

Defines the resource to request. This can either be a string containing the URL of the resource, or an existing [`Request`](global-Request) object to copy.

**`options`** (optional)

An object containing options to configure the request. It accepts the same properties as the `init` argument of [`fetch`](global-fetch#parameters), such as `method`, `headers`, `body`, `credentials` and `signal`.

## Instance properties

### `method`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/method).

The request's method (`"GET"`, `"POST"`, etc.).

### `url`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/url).

The URL of the request.

### `headers`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/headers).

The [`Headers`](global-Headers) object associated with the request.

### `credentials`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials).

Indicates whether the user agent should send or receive cookies for the request. Defaults to `"same-origin"`.

### `bodyUsed`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/bodyUsed).

A boolean indicating whether the body has already been read.

## Instance methods

### `clone()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/clone).

Creates a copy of the current `Request` object.

### `arrayBuffer()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/arrayBuffer).

Returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representation of the request body.

### `blob()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/blob).

Returns a promise that resolves with a [`Blob`](global-Blob) representation of the request body.

### `formData()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/formData).

Returns a promise that resolves with a `FormData` representation of the request body.

### `json()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/json).

Returns a promise that resolves with the result of parsing the request body as JSON.

### `text()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request/text).

Returns a promise that resolves with a string representation of the request body.

:::warning[Partial support]

Because `Request` is provided by the `whatwg-fetch` polyfill running on top of [`XMLHttpRequest`](global-XMLHttpRequest), some standard properties are not available. In particular, the `body` property (a `ReadableStream`) is not supported, so request bodies cannot be streamed. Options such as `cache`, `redirect`, `mode`, `referrer` and `keepalive` are ignored.

For anything not covered here, refer to the [`whatwg-fetch` documentation](https://github.com/github/fetch) and the [`Request` documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Request).

:::
