---
id: global-console
title: console
---

The global [`console`](https://developer.mozilla.org/en-US/docs/Web/API/console) object, as defined in Web specifications. It provides access to the debugging console, with methods for logging, grouping, timing, and more.

React Native supports the standard `console` methods (such as `console.log`, `console.warn`, and `console.error`). Refer to the [MDN documentation](https://developer.mozilla.org/en-US/docs/Web/API/console) for details on the standard API.

---

# Reference

## Methods

For the standard methods, see the [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/console).

### `timeStamp()` ⚠️

:::warning[Non-standard]
This is a React Native / DevTools specific extension.
:::

```tsx
console.timeStamp(
  label: string,
  start?: string | number,
  end?: string | number,
  trackName?: string,
  trackGroup?: string,
  color?: DevToolsColor
): void;
```

The `console.timeStamp` API allows you to add custom timing entries in the Performance panel timeline.

**Parameters:**

| Name       | Type               | Required | Description                                                                                                                                                                                                                                                                                                   |
| ---------- | ------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| label      | `string`           | Yes      | The label for the timing entry.                                                                                                                                                                                                                                                                               |
| start      | `string \| number` | No       | <ul><li>If string, the name of a previously recorded timestamp with `console.timeStamp`.</li><li>If number, the [DOMHighResTimeStamp](https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp). For example, from `performance.now()`.</li><li>If undefined, the current time is used.</li></ul> |
| end        | `string \| number` | No       | <ul><li>If string, the name of a previously recorded timestamp with `console.timeStamp`.</li><li>If number, the [DOMHighResTimeStamp](https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp). For example, from `performance.now()`.</li><li>If undefined, the current time is used.</li></ul> |
| trackName  | `string`           | No       | The name of the custom track.                                                                                                                                                                                                                                                                                 |
| trackGroup | `string`           | No       | The name of the track group.                                                                                                                                                                                                                                                                                  |
| color      | `DevToolsColor`    | No       | The color of the entry.                                                                                                                                                                                                                                                                                       |

```tsx
type DevToolsColor =
  | 'primary'
  | 'primary-light'
  | 'primary-dark'
  | 'secondary'
  | 'secondary-light'
  | 'secondary-dark'
  | 'tertiary'
  | 'tertiary-light'
  | 'tertiary-dark'
  | 'warning'
  | 'error';
```
