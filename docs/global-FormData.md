---
id: global-FormData
title: FormData
---

The global [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData) class, as defined in Web specifications. It provides a way to construct a set of key/value pairs representing form fields and their values, which can then be sent in a multipart request body using [`fetch()`](global-fetch) or [`XMLHttpRequest`](global-XMLHttpRequest).

In React Native, a form field value can be either a string or a native file, represented as an object with a `uri` property (and optional `name` and `type` properties).

:::warning[Partial support]
React Native's `FormData` is a partial implementation. It only supports the [`append()`](#append) and [`getAll()`](#getall) methods. The standard `get()`, `has()`, `set()`, `delete()`, `entries()`, `keys()`, `values()`, and `forEach()` methods are **not** implemented. Values are also restricted to strings and native file objects; the Web-standard [`Blob`](global-Blob)/[`File`](global-File) values are not supported.
:::

---

# Reference

## Constructor

### `FormData()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FormData/FormData).

Creates a new, empty `FormData` object.

```ts
new FormData();
```

:::warning[Partial support]
Unlike the Web specification, React Native's constructor does not accept an HTML `<form>` element or any other arguments.
:::

## Instance methods

### `append()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FormData/append).

Appends a new value onto an existing key, or adds the key if it does not already exist. Duplicate keys are allowed; each appended value is sent as an additional part in the request body.

```ts
append(name, value);
```

#### Parameters

| Name    | Type             | Description                                                                                                                          |
| ------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `name`  | string           | The name of the field. Required.                                                                                                     |
| `value` | string \| object | The field value. Either a string, or a native file object with a `uri` property and optional `name` and `type` properties. Required. |

### `getAll()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/FormData/getAll).

Returns an array of all the values associated with a given key. Returns an empty array if the key does not exist.

```ts
getAll(name);
```

#### Parameters

| Name   | Type   | Description                                  |
| ------ | ------ | -------------------------------------------- |
| `name` | string | The name of the field to retrieve. Required. |
