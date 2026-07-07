---
id: global-MutationRecord
title: MutationRecord 🧪
---

import CanaryAPIWarning from './\_canary-channel-api-warning.mdx';

<CanaryAPIWarning />

The global [`MutationRecord`](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord) interface, as defined in Web specifications. It is a read-only interface that represents an individual mutation observed by a [`MutationObserver`](global-MutationObserver).

Instances of `MutationRecord` are delivered to a `MutationObserver` callback in its `mutationRecords` parameter.

---

# Reference

## Instance properties

### `addedNodes`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/addedNodes).

Returns a [`NodeList`](nodes) of the nodes added by the mutation. Will be empty if no nodes were added.

### `attributeName`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/attributeName).

Returns `null`.

:::warning[Partial support]
Attribute mutations are not supported in React Native.
:::

### `nextSibling`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/nextSibling).

Returns the next sibling of the added or removed nodes, or `null`.

### `oldValue`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/oldValue).

Returns `null`.

:::warning[Partial support]
Attribute and character data mutations are not supported in React Native, so an old value is never recorded.
:::

### `previousSibling`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/previousSibling).

Returns the previous sibling of the added or removed nodes, or `null`.

### `removedNodes`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/removedNodes).

Returns a [`NodeList`](nodes) of the nodes removed by the mutation. Will be empty if no nodes were removed.

### `target`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/target).

Returns the [`Element`](element-nodes) whose children changed.

### `type`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord/type).

Returns the type of mutation. In React Native this is always `"childList"`, as it is the only supported mutation type.
