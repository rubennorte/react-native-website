---
id: global-URL
title: URL
---

The global [`URL`](https://developer.mozilla.org/en-US/docs/Web/API/URL) class, as defined in Web specifications. It is used to parse, construct, normalize, and read the components of a URL.

:::warning[Partial support]
React Native provides a **partial, non-spec-compliant** implementation of `URL`. It is based on regular expression parsing rather than the full [WHATWG URL parsing algorithm](https://url.spec.whatwg.org/), so it may not handle all URLs correctly (in particular it assumes `http`/`https` URLs when reading most components).

Most components are exposed as **read-only getters** (unlike the standard, where they are writable). Only `search` provides a setter. If you need full spec compliance, consider a polyfill such as [`react-native-url-polyfill`](https://github.com/charpeni/react-native-url-polyfill).
:::

`URL` is closely related to [`URLSearchParams`](global-URLSearchParams), which represents the query string, and to [`Blob`](global-Blob), for which React Native can create object URLs.

---

# Reference

## Constructor

### `URL()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL).

Creates and returns a new `URL` object representing the URL defined by the parameters.

```ts
new URL(url, base?)
```

#### Parameters

**`url`**

A string representing an absolute or relative URL. If `url` is a relative URL, `base` is required and is used to resolve the final URL.

**`base`** (optional)

A string or `URL` representing the base URL to use in cases where `url` is a relative URL. If not provided, `url` must be an absolute URL.

## Static methods

### `createObjectURL()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL_static).

Creates a string containing a URL representing the given [`Blob`](global-Blob) object. The URL can later be used to reference the blob's contents.

```ts
static createObjectURL(blob)
```

:::warning[Partial support]
Only [`Blob`](global-Blob) objects are supported (the standard also allows `MediaSource`). Object URLs are only available if the native Blob module is present; otherwise this method throws.
:::

#### Parameters

**`blob`**

The [`Blob`](global-Blob) for which to create an object URL.

### `revokeObjectURL()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL_static).

Releases an existing object URL previously created by calling `createObjectURL()`.

```ts
static revokeObjectURL(url)
```

:::warning[Partial support]
In React Native this method is a no-op. Object URLs remain valid for the lifetime of the referenced [`Blob`](global-Blob) and are not explicitly released.
:::

#### Parameters

**`url`**

A string representing an object URL that was previously created by calling `createObjectURL()`.

## Instance properties

:::warning[Partial support]
With the exception of `search`, all of the properties below are **read-only** in React Native. In the standard, most of them are writable setters that update the URL. Values are derived by regular expression parsing and assume an `http`/`https` URL.
:::

### `hash`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/hash).

A string containing a `'#'` followed by the fragment identifier of the URL. Read-only in React Native.

### `host`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/host).

A string containing the host, that is the hostname, and then, if the port of the URL is nonempty, a `':'`, followed by the port. Read-only in React Native.

### `hostname`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/hostname).

A string containing the domain of the URL. Read-only in React Native.

### `href`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/href).

A string containing the whole URL. Read-only in React Native.

### `origin`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/origin).

A string containing the origin of the URL, that is its scheme, its domain, and its port. Read-only.

### `password`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/password).

A string containing the password specified before the domain name. Read-only in React Native.

### `pathname`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname).

A string containing an initial `'/'` followed by the path of the URL, not including the query string or fragment. Read-only in React Native.

### `port`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/port).

A string containing the port number of the URL. Read-only in React Native.

### `protocol`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/protocol).

A string containing the protocol scheme of the URL, including the final `':'`. Read-only in React Native.

### `search`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/search).

A string containing a `'?'` followed by the parameters or query string of the URL. This is the only writable property in React Native; setting it updates the URL and resets the associated [`searchParams`](#searchparams) object.

```ts
get search(): string;
set search(value: string): void;
```

### `searchParams`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams).

A [`URLSearchParams`](global-URLSearchParams) object which can be used to access the individual query parameters found in `search`.

:::warning[Partial support]
The `searchParams` object is created lazily from the current `search` value. Mutating it is reflected when reading `href`/`toString()`, but the standard behavior of keeping `search` and `searchParams` fully in sync at all times is not guaranteed.
:::

### `username`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/username).

A string containing the username specified before the domain name. Read-only in React Native.

## Instance methods

### `toJSON()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON).

Returns a string containing the whole URL. It returns the same string as the [`href`](#href) property.

```ts
toJSON(): string
```

### `toString()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URL/toString).

Returns a string containing the whole URL, including any pending changes made through [`searchParams`](#searchparams).

```ts
toString(): string
```
