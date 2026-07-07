---
id: global-WebSocket
title: WebSocket
---

The global [`WebSocket`](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket) class, as defined in Web specifications. It provides the API for creating and managing a WebSocket connection to a server, as well as for sending and receiving data over the connection.

In React Native, `WebSocket` is implemented on top of the native networking APIs and extends [`EventTarget`](global-EventTarget). Binary messages can be exchanged as [`Blob`](global-Blob) or `ArrayBuffer` values (see [`binaryType`](#binarytype)).

---

# Reference

## Constructor

### `WebSocket()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/WebSocket).

Creates a new `WebSocket` object and immediately attempts to connect to the given URL.

```ts
new WebSocket(url, protocols?, options?)
```

#### Parameters

**`url`**

A string representing the URL to which to connect. This should be the URL to which the WebSocket server will respond (typically using the `ws://` or `wss://` scheme).

**`protocols`** (optional)

Either a single protocol string or an array of protocol strings used to indicate sub-protocols, so that a single server can implement multiple WebSocket sub-protocols.

**`options`** ⚠️ (optional)

:::warning[Non-standard]
This is a React Native specific extension.
:::

An optional object used to configure the connection. It supports the following property:

| Name      | Type   | Description                                                                                                       |
| --------- | ------ | ----------------------------------------------------------------------------------------------------------------- |
| `headers` | object | An object of additional HTTP headers to send during the handshake, for example `{origin: 'https://example.com'}`. |

## Static properties

The following constants describe the value of the [`readyState`](#readystate) property. They are also available as instance properties.

### `WebSocket.CONNECTING`

Returns `0`. The connection is not yet open.

### `WebSocket.OPEN`

Returns `1`. The connection is open and ready to communicate.

### `WebSocket.CLOSING`

Returns `2`. The connection is in the process of closing.

### `WebSocket.CLOSED`

Returns `3`. The connection is closed or could not be opened.

## Instance properties

### `binaryType`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/binaryType).

Gets or sets the type used for binary data received over the connection. In React Native the supported values are `'blob'` and `'arraybuffer'`. Setting an invalid value throws an error, and using `'blob'` requires the native `BlobModule` to be available.

### `bufferedAmount`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/bufferedAmount).

Returns the number of bytes of data that have been queued using [`send()`](#send) but not yet transmitted to the network.

### `extension`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/extensions).

Returns the extensions selected by the server, if any.

### `protocol`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/protocol).

Returns the sub-protocol selected by the server, if any.

### `readyState`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/readyState).

Returns the current state of the connection, as one of the constants listed in [Static properties](#static-properties).

### `url`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/url).

Returns the URL that was used to establish the connection.

## Instance methods

### `close()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/close).

Closes the WebSocket connection or connection attempt, if any.

```ts
close(code?, reason?)
```

#### Parameters

**`code`** (optional)

A numeric status code explaining why the connection is being closed. Defaults to `1000` (normal closure).

**`reason`** (optional)

A human-readable string explaining why the connection is closing.

### `send()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket/send).

Enqueues the specified data to be transmitted to the server over the WebSocket connection. The data can be a string, an `ArrayBuffer`, an `ArrayBufferView`, or a [`Blob`](global-Blob). Throws if the connection is still in the `CONNECTING` state.

```ts
send(data);
```

### `ping()` ⚠️

:::warning[Non-standard]
This is a React Native specific extension.
:::

Sends a WebSocket ping control frame to the server. Throws if the connection is still in the `CONNECTING` state.

```ts
ping();
```

## Events

`WebSocket` dispatches `open`, `message`, `error` and `close` events, which can be observed with [`addEventListener()`](global-EventTarget#addeventlistener) or via the corresponding `onopen`, `onmessage`, `onerror` and `onclose` handler properties.

:::warning[Partial support]
The `close` event's `wasClean` property is not currently populated in React Native.
:::
