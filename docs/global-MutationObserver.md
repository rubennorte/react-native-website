---
id: global-MutationObserver
title: MutationObserver 🧪
---

import CanaryAPIWarning from './\_canary-channel-api-warning.mdx';

<CanaryAPIWarning />

The global [`MutationObserver`](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) interface, as defined in Web specifications. It provides the ability to watch for changes being made to the native view tree.

:::warning[Partial support]
React Native only supports observing changes to the list of children of an element (the `childList` option, which must be set to `true`). Observing attribute or character data mutations is not supported.
:::

---

# Reference

## Constructor

### `MutationObserver()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/MutationObserver).

Creates a new `MutationObserver` object which will invoke a specified callback function when DOM changes occur.

```ts
new MutationObserver(callback);
```

#### Parameters

**`callback`**

A function which is called when there are mutations observed on any of the target nodes. The callback receives two parameters:

- `mutationRecords`: An array of [`MutationRecord`](global-MutationRecord) objects describing each change that occurred.
- `observer`: The `MutationObserver` instance which invoked the callback.

## Instance methods

### `observe()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/observe).

Configures the `MutationObserver` to begin receiving notifications through its callback function when DOM changes matching the given options occur.

```ts
observe(target, options?)
```

#### Parameters

**`target`**

An [`Element`](element-nodes) (obtained from a component ref) whose children should be observed.

**`options`** (optional)

An object with the following properties:

| Name        | Type    | Description                                                                                                                        |
| ----------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `childList` | true    | **Required.** Must be set to `true`, as it is the only supported option. Observes additions and removals of the target's children. |
| `subtree`   | boolean | Whether mutations of not just the target, but also the target's descendants should be observed. Defaults to `false`.               |

### `disconnect()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/disconnect).

Stops the `MutationObserver` from receiving further notifications until and unless `observe()` is called again. The observer can be reused by calling its `observe()` method again.

### `takeRecords()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/takeRecords).

Returns an array of the [`MutationRecord`](global-MutationRecord) objects that have been detected but not yet processed by the observer's callback function, leaving the mutation queue empty.
