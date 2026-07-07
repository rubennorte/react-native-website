---
id: global-navigator
title: navigator
---

The global [`navigator`](https://developer.mozilla.org/en-US/docs/Web/API/Window/navigator) object, as defined in Web specifications. In React Native it is a minimal object primarily used for feature detection.

:::warning[Partial support]
React Native provides a minimal `navigator` object. Unlike the Web, it is **not** an instance of `Navigator` and most standard properties and methods (such as `onLine`, `userAgent`, or `geolocation`) are not available.

The only property guaranteed by React Native is [`product`](#product), which always has the value `'ReactNative'`. Additional properties (for example `geolocation`) may be attached by community modules but are not part of React Native itself.
:::

---

# Reference

## Instance properties

### `product`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/product).

Always returns the string `'ReactNative'`. This is commonly used for feature detection to determine whether code is running in a React Native environment.

```ts
navigator.product; // 'ReactNative'
```
