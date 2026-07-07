---
id: global-XMLHttpRequest
title: XMLHttpRequest
---

The global [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) class, as defined in Web specifications. It is used to interact with servers, allowing you to retrieve data from a URL without having to do a full page refresh.

In React Native, `XMLHttpRequest` is implemented on top of the native networking APIs and is the foundation of higher-level networking, including [`fetch`](global-fetch). It extends [`EventTarget`](global-EventTarget).

---

# Reference

## Constructor

### `XMLHttpRequest()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/XMLHttpRequest).

Creates a new `XMLHttpRequest` object.

```ts
new XMLHttpRequest();
```

## Static properties

The following constants describe the value of the [`readyState`](#readystate) property. They are also available as instance properties.

### `XMLHttpRequest.UNSENT`

Returns `0`. The client has been created, but `open()` has not been called yet.

### `XMLHttpRequest.OPENED`

Returns `1`. `open()` has been called.

### `XMLHttpRequest.HEADERS_RECEIVED`

Returns `2`. `send()` has been called, and headers and status are available.

### `XMLHttpRequest.LOADING`

Returns `3`. The response is being downloaded; [`responseText`](#responsetext) holds partial data.

### `XMLHttpRequest.DONE`

Returns `4`. The operation is complete.

## Instance properties

### `readyState`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState).

Returns the state of the request, as one of the constants listed in [Static properties](#static-properties).

### `response`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/response).

Returns the response body, whose type depends on [`responseType`](#responsetype).

### `responseHeaders` ⚠️

:::warning[Non-standard]
This is a React Native specific extension.
:::

Returns the raw response headers as an object, or `null` if no response has been received. Use the standard [`getResponseHeader()`](#getresponseheader) and [`getAllResponseHeaders()`](#getallresponseheaders) methods for spec-compliant access.

### `responseText`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText).

Returns the text response. Accessing this property throws if [`responseType`](#responsetype) is set to anything other than `''` or `'text'`.

### `responseType`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType).

Gets or sets the type of the response. Supported values in React Native are `''` (default, treated as text), `'text'`, `'json'`, `'arraybuffer'` and `'blob'`.

:::warning[Partial support]
The `'document'` response type is **not supported** in React Native (there is no DOM `Document`). The `'blob'` type additionally requires the native `BlobModule` to be available. Setting `responseType` after the request has been sent throws an error.
:::

### `responseURL`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseURL).

Returns the serialized URL of the response, or an empty string if the URL is null.

### `status`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status).

Returns the HTTP status code of the response.

### `timeout`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout).

Gets or sets the number of milliseconds a request can take before being automatically terminated. Defaults to `0` (no timeout). When a request times out, a `timeout` event is dispatched.

### `upload`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/upload).

Returns an `XMLHttpRequestEventTarget` object that can be used to monitor upload progress via `progress` events.

### `withCredentials`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials).

A boolean indicating whether cross-site requests should be made using credentials such as cookies. In React Native this defaults to `true`.

## Instance methods

### `abort()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort).

Aborts the request if it has already been sent.

### `getAllResponseHeaders()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getAllResponseHeaders).

Returns all the response headers, separated by CRLF, as a string, or `null` if no response has been received.

### `getResponseHeader()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/getResponseHeader).

Returns the string value of a given response header, or `null` if the header does not exist. Header matching is case-insensitive.

### `open()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/open).

Initializes a request.

```ts
open(method, url, async?)
```

#### Parameters

**`method`**

The HTTP request method to use, e.g. `"GET"`, `"POST"`, `"PUT"`, `"DELETE"`.

**`url`**

A string representing the URL to send the request to.

**`async`** (optional)

Only asynchronous requests are supported. Passing `false` throws an error. The `user` and `password` arguments defined by the standard are not supported.

### `send()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send).

Sends the request. If the request is asynchronous (which it always is in React Native), this method returns as soon as the request is sent.

```ts
send(data?)
```

### `setRequestHeader()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/setRequestHeader).

Sets the value of an HTTP request header. Must be called after [`open()`](#open) but before [`send()`](#send).

### `setTrackingName()` ⚠️

:::warning[Non-standard]
This is a React Native specific extension.
:::

Associates a human-readable name with the request, used to identify the origin of the request (for example in network inspectors and performance logs). Returns the `XMLHttpRequest` instance for chaining.

```ts
setTrackingName(trackingName);
```

### `setPerformanceLogger()` ⚠️

:::warning[Non-standard]
This is a React Native specific extension.
:::

Attaches a performance logger that receives a `network_XMLHttpRequest_<name>` start/stop timespan around each dispatched request. The logger only needs to implement `startTimespan(key)` and `stopTimespan(key)`. Returns the `XMLHttpRequest` instance for chaining.

```ts
setPerformanceLogger(performanceLogger);
```

## Events

`XMLHttpRequest` dispatches standard events such as `readystatechange`, `loadstart`, `progress`, `load`, `error`, `abort`, `timeout` and `loadend`. These can be observed with [`addEventListener()`](global-EventTarget#addeventlistener) or via the corresponding `on<event>` handler properties (e.g. `onreadystatechange`, `onload`, `onerror`, `ontimeout`).

:::warning[Partial support]
Synchronous requests are not supported. Only asynchronous behavior is available regardless of the `async` argument passed to [`open()`](#open). The `'document'` [`responseType`](#responsetype) is not supported.
:::
