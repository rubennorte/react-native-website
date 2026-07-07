---
id: global-alert
title: alert
---

The global [`alert`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert) function, as defined in Web specifications. It displays a modal dialog with a message, mapping to the React Native [Alert](alert) API.

:::warning[Partial support]
React Native's `alert` differs from the Web `window.alert`:

- It only accepts a single `message` argument (additional arguments are ignored).
- It displays a native dialog titled `"Alert"`, rendered by the [Alert](alert) API.
- The native dialog is shown asynchronously and does not block JavaScript execution, so `alert` returns no value.

For more control over the dialog (custom title, buttons, etc.), use the [Alert](alert) API directly.
:::

---

# Reference

## Methods

### `alert()`

See [documentation in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert).

Displays a native alert dialog with the given message.

```ts
alert(message: string): void
```

#### Parameters

**`message`**

The string to display in the alert dialog. Non-string values are coerced to a string.
