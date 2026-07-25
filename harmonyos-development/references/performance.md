# HarmonyOS Performance Reference

Use this file for ArkUI performance, large lists, rendering, memory, and startup reviews.

## Checklist

- Prefer `LazyForEach` for large or dynamic lists.
- Use stable keys for list items.
- Avoid excessive nested layout containers.
- Avoid heavy work in render/build functions.
- Move IO, parsing, and expensive computation out of UI rendering.
- Use component reuse only when it matches the target SDK and the page pattern.
- Check image size, decode cost, cache policy, and lazy loading.
- Check ability lifecycle side effects and resource cleanup.

## Debug questions

Ask for:

- target SDK
- device model or emulator
- page route
- reproduction steps
- HiLog / AppFreeze / performance report
- screenshot or screen recording when UI jank is visual

## Memory-leak diagnostics

Use the smallest tool that can identify the suspected leak:

| Suspected area | Prefer |
|---|---|
| ArkTS component or lifecycle object | `@ohos.hiviewdfx.jsLeakWatcher` during development |
| ArkTS heap retention path | DevEco Studio JS Heap / heap snapshot |
| Native allocation or free error | HWASan / AddrSanitizer in development or test |
| Runtime freeze or resource pressure | AppFreeze, HiAppEvent, HiLog, DevEco Testing |

`jsLeakWatcher` periodically checks whether registered lifecycle objects remain alive after they should be collectible. It is intended primarily for development. If production diagnosis is unavoidable, use a small gray-release population rather than enabling it permanently for all users.

Do not claim a leak is fixed from one heap snapshot. Reproduce the lifecycle, force or wait for collection as appropriate, compare retained objects, fix the ownership path, and repeat the same scenario.

Official reference: https://developer.huawei.com/consumer/cn/doc/best-practices/bpta-stability-memleak-detection-overview

## Output rule

Give prioritized fixes: quick wins first, then structural changes, then SDK/tooling checks.
