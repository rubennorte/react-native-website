---
id: global-clearImmediate
title: clearImmediate ⚠️
---

:::warning[Non-standard]
`clearImmediate` is not part of any Web standard. React Native provides it for compatibility with existing code and libraries (it also exists in [Node.js](https://developer.mozilla.org/en-US/docs/Web/API/Window/clearImmediate)).
:::

The global `clearImmediate` function cancels an action previously scheduled with [`setImmediate()`](global-setImmediate).

---

# Reference

```ts
clearImmediate(id);
```

#### Parameters

**`id`**

The ID returned by the corresponding call to [`setImmediate()`](global-setImmediate).
