---
id: global-Headers
title: Headers
---

The global [`Headers`](https://developer.mozilla.org/en-US/docs/Web/API/Headers) class, as defined in Web specifications. It represents the set of HTTP headers associated with a request or response, and provides methods to add, read, remove and iterate over them.

In React Native, `Headers` is provided by the [`whatwg-fetch`](https://github.com/github/fetch) polyfill and is used together with [`fetch`](global-fetch), [`Request`](global-Request) and [`Response`](global-Response).

---

# Reference

## Constructor

### `Headers()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/Headers).

Creates a new `Headers` object.

```ts
new Headers(init?)
```

#### Parameters

**`init`** (optional)

An object used to prefill the headers. It can be another [`Headers`](global-Headers) object, an object literal with string values, or an array of `[name, value]` string pairs.

## Instance methods

### `append()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/append).

Appends a new value onto an existing header, or adds the header if it does not already exist.

### `delete()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/delete).

Deletes a header from the `Headers` object.

### `get()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/get).

Returns a string of all the values of a header with the given name, or `null` if the header does not exist.

### `has()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/has).

Returns a boolean indicating whether a header with the given name exists.

### `set()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/set).

Sets a new value for an existing header, or adds the header if it does not already exist. Unlike `append()`, it overwrites any existing value.

### `forEach()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/forEach).

Executes a provided function once for each key/value pair in the `Headers` object.

### `keys()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/keys).

Returns an iterator allowing you to go through all the keys of the key/value pairs contained in the object.

### `values()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/values).

Returns an iterator allowing you to go through all the values of the key/value pairs contained in the object.

### `entries()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Headers/entries).

Returns an iterator allowing you to go through all the key/value pairs contained in the object.
