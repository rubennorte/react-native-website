---
id: global-URLSearchParams
title: URLSearchParams
---

The global [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) class, as defined in Web specifications. It provides utility methods to work with the query string of a URL.

`URLSearchParams` is closely related to [`URL`](global-URL), whose [`searchParams`](global-URL#searchparams) property returns a `URLSearchParams` instance.

:::warning[Partial support]
React Native provides a small custom implementation of `URLSearchParams` that covers the common surface. Parsing and serialization are simplified compared to the [WHATWG URL specification](https://url.spec.whatwg.org/#urlsearchparams), so edge cases (in particular around Unicode encoding) may not match browser behavior.
:::

---

# Reference

## Constructor

### `URLSearchParams()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/URLSearchParams).

Creates and returns a new `URLSearchParams` object.

```ts
new URLSearchParams(init?)
```

#### Parameters

**`init`** (optional)

One of the following, used to initialize the query parameters:

| Type                     | Description                                                                         |
| ------------------------ | ----------------------------------------------------------------------------------- |
| string                   | A query string, with or without a leading `'?'` (e.g. `"key1=value1&key2=value2"`). |
| `[string, string][]`     | An array of key/value pairs (e.g. `[["key1", "value1"], ["key2", "value2"]]`).      |
| `Record<string, string>` | A record of string keys to string values (e.g. `{key1: "value1", key2: "value2"}`). |

## Instance properties

### `size`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/size).

Returns the total number of parameter entries.

:::warning[Partial support]
In React Native `size` returns the number of distinct keys rather than the total number of key/value pairs. Keys with multiple values are counted once.
:::

## Instance methods

### `append()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/append).

Appends a specified key/value pair as a new search parameter.

```ts
append(name, value): void
```

### `delete()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/delete).

Deletes search parameters that match a given name.

```ts
delete(name): void
```

:::warning[Partial support]
The optional `value` argument (deleting only entries whose value also matches) is not supported. All entries with the given name are removed.
:::

### `entries()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/entries).

Returns an iterator allowing iteration through all key/value pairs contained in this object.

```ts
entries(): Iterator<[string, string]>
```

### `forEach()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/forEach).

Allows iteration through all values contained in this object via a callback function.

```ts
forEach(callback): void
```

### `get()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/get).

Returns the first value associated with the given search parameter, or `null` if none exists.

```ts
get(name): string | null
```

### `getAll()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/getAll).

Returns all the values associated with a given search parameter as an array.

```ts
getAll(name): string[]
```

### `has()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/has).

Returns a boolean indicating whether a parameter with the specified name exists.

```ts
has(name): boolean
```

:::warning[Partial support]
The optional `value` argument (checking for a specific name/value pair) is not supported. Only the name is considered.
:::

### `keys()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/keys).

Returns an iterator allowing iteration through all keys of the key/value pairs contained in this object.

```ts
keys(): Iterator<string>
```

### `set()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/set).

Sets the value associated with a given search parameter to the given value. If there are several matching values, this method deletes the others. If the parameter does not exist, it is created.

```ts
set(name, value): void
```

### `sort()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/sort).

Sorts all key/value pairs, if any, by their keys.

```ts
sort(): void
```

### `values()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/values).

Returns an iterator allowing iteration through all values of the key/value pairs contained in this object.

```ts
values(): Iterator<string>
```

### `toString()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/toString).

Returns a query string suitable for use in a URL. Spaces are encoded as `'+'`.

```ts
toString(): string
```

### `[Symbol.iterator]()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/Symbol.iterator).

Returns an iterator allowing iteration through all key/value pairs contained in this object. Equivalent to [`entries()`](#entries), enabling use with `for...of`.

```ts
[Symbol.iterator](): Iterator<[string, string]>
```
