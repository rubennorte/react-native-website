---
id: global-requestIdleCallback
title: requestIdleCallback
---

The global [`requestIdleCallback`](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback) function, as defined in Web specifications. It queues a function to be called during a browser's idle periods, letting you run low-priority work without impacting latency-critical events.

---

# Reference

## Methods

### `requestIdleCallback()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestIdleCallback).

Schedules a callback to be invoked during a period when the JavaScript thread is idle, i.e. when there is time left in the current frame after higher-priority work has completed.

```ts
requestIdleCallback(callback, options?): number
```

#### Parameters

**`callback`**

A function to call when there is idle time available. The callback receives a deadline object with the following members:

- `timeRemaining()`: A function returning the estimated number of milliseconds remaining in the current idle period. In React Native, the remaining time is capped to the time left in the current frame (based on a 60 FPS budget of roughly 16.67&nbsp;ms).
- `didTimeout`: A boolean that is `true` if the callback is being executed because the `timeout` specified in `options` elapsed before the callback could otherwise be run.

**`options`** (optional)

An object that may contain the following property:

| Name      | Type   | Description                                                                                                                                                               |
| --------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `timeout` | number | If provided, the callback is invoked after this many milliseconds even if no idle period has occurred yet. When it fires due to the timeout, `didTimeout` will be `true`. |

#### Returns

A positive number (the request identifier) that can be passed to [`cancelIdleCallback()`](global-cancelIdleCallback) to cancel the scheduled callback.

:::warning[Partial support]
In React Native, idle callbacks are scheduled per frame rather than during genuine browser-style idle periods. A callback only runs if at least 1&nbsp;ms is left in the current frame, and `timeRemaining()` never reports more than the time left in the current frame. The only supported option is `timeout`.
:::
