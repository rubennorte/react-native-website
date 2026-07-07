---
id: global-TaskAttributionTiming
title: TaskAttributionTiming
---

The global [`TaskAttributionTiming`](https://developer.mozilla.org/en-US/docs/Web/API/TaskAttributionTiming) class, as defined in Web specifications. It provides information about the work involved in a long task and its associated frame context.

Instances of `TaskAttributionTiming` are exposed through the `attribution` property of [`PerformanceLongTaskTiming`](global-PerformanceLongTaskTiming) entries.

:::warning[Partial support]
The `attribution` property of `PerformanceLongTaskTiming` is always an empty array, so no `TaskAttributionTiming` entries are currently produced.
:::
