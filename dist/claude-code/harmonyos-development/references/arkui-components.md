# ArkUI Components Reference

Use this reference when the user asks about ArkUI layout, components, rendering, interaction, or page implementation.

## Defaults

- Prefer declarative ArkUI component examples in `.ets` files.
- Use HarmonyOS-native components and APIs instead of React, DOM, Android View, or Jetpack Compose patterns.
- State the target SDK assumption when behavior depends on SDK version.

## Component guidance

| Need | Prefer |
|---|---|
| Vertical layout | `Column` |
| Horizontal layout | `Row` |
| Overlay / layered layout | `Stack` |
| Flexible wrapping layout | `Flex` |
| Large lists | `List` + `LazyForEach` |
| Grid content | `Grid` / `GridItem` |
| Layout that responds to its containing component | `ContainerReader` container breakpoints |
| Paged tabs | `Tabs` / `TabContent` |
| Swipe carousel | `Swiper` |
| Navigation shell | `Navigation` / `NavDestination` |

## Review checklist

- Keep layout nesting reasonable.
- Avoid heavy computation inside `build()`.
- Use stable keys for dynamic list rendering.
- Keep component state ownership clear.
- Include permission, routing, or module configuration when the component depends on it.

## Container-responsive layout

Use `ContainerReader` when a reusable component must change layout according to its own container instead of the application window. This is more precise than a window breakpoint for sidebars, split views, nested panes, and reusable cards.

Do not replace `ContainerReader` with a one-time window-width query. Keep the breakpoint decision attached to the container so it updates when the parent layout changes.

## Global component reuse

API 26 documentation adds centralized global reuse pools for `@Reusable` and `@ReusableV2` components. Use them only for components whose lifecycle and state-reset behavior are designed for reuse:

- release heavy resources in the recycle lifecycle;
- reset transient state before reused content becomes visible;
- keep reuse identifiers stable and compatible with the target SDK;
- profile first, because reuse adds lifecycle complexity and is not automatically faster for small pages.

Official update summary: https://developer.huawei.com/consumer/cn/monthly/202606
