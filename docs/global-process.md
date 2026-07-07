---
id: global-process
title: process
---

The global `process` object, as defined in Node.js. In React Native it is a minimal shim rather than the full Node.js `process` object.

:::warning[Partial support]
React Native provides a minimal, Node-like `process` shim. It is **not** the full Node.js `process` object, and most of its properties and methods are unavailable.

The property React Native guarantees is [`process.env.NODE_ENV`](#env), which is set to `'development'` or `'production'`. Additional properties may be added by Metro or community tooling, but they are not part of React Native itself.
:::

---

# Reference

## Instance properties

### `env`

An object containing environment variables.

React Native populates `process.env.NODE_ENV` with either `'development'` or `'production'`, depending on how the application bundle was built. This is commonly used to guard development-only code.

```ts
if (process.env.NODE_ENV === 'development') {
  // Development-only code
}
```
