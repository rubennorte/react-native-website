---
id: global-requestAnimationFrame
title: requestAnimationFrame
---

The global [`requestAnimationFrame`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame) function, as defined in Web specifications.

In React Native it exists mainly as a compatibility mechanism for libraries that expect it to be available. It is currently implemented as a [`setTimeout()`](global-setTimeout) with a delay close to `0`, so the callback is **not** synchronized with the display's refresh rate or the rendering of the next frame.

:::warning[Not for animations]

`requestAnimationFrame` should not be used to drive animations in React Native. Because the callback runs on the JavaScript thread and is not tied to frame rendering, animations driven this way can drop frames and feel janky.

Animations should instead be driven natively, on the UI thread, using libraries such as [`Animated`](animated) (with the native driver) or [Reanimated](https://docs.swmansion.com/react-native-reanimated/).

:::

---

# Reference

## Methods

### `requestAnimationFrame()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame).

Schedules the callback to be invoked on the next frame. See the note at the top of this page for its limitations in React Native.

```ts
requestAnimationFrame(callback): number
```

#### Parameters

**`callback`**

The function to call on the next frame. The callback is passed a single argument: a timestamp (in milliseconds, consistent with [`performance.now()`](https://developer.mozilla.org/en-US/docs/Web/API/Performance/now)) indicating the time at which the callback is invoked.

#### Returns

A positive number (the request identifier) that can be passed to [`cancelAnimationFrame()`](global-cancelAnimationFrame) to cancel the scheduled callback.
