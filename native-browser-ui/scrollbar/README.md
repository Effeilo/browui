<div align="center">
  <img src="./../../assets/scrollbar.svg" alt="logo scrollbar" width="150"/>
  <h1>Themed scrollbar</h1>
</div>

A native scrollbar customization layer using standard Firefox properties and WebKit scrollbar pseudo-elements. The `.ui-scrollbar` utility applies the same themed behavior to custom scrollable containers without hardcoding visual styles.

## At a glance

- 0 KB JavaScript
- 35 CSS lines
- native scrollbars
- native fallback

## Files

- `scrollbar.css`: CSS mechanisms and theme hooks from the component snippet.

## CSS mechanisms

- Scrollbar Styling

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Standard scrollbar colors | `scrollbar-color` | Recent | 121+ | 121+ | 64+ | 26.2+ | [Can I Use](https://caniuse.com/mdn-css_properties_scrollbar-color) |
| Standard scrollbar width | `scrollbar-width` | Stable | 121+ | 121+ | 64+ | 18.2+ | [Can I Use](https://caniuse.com/mdn-css_properties_scrollbar-width) |
| WebKit scrollbar parts | `::-webkit-scrollbar` | Partial | 4+ | 79+ | - | 4+ | [Can I Use](https://caniuse.com/css-scrollbar) |

## Benefits

- **Native UI**: The scrollbar remains the browser's native control. Scrolling behavior, input handling, and platform conventions stay intact.
- **Theme tokens**: Visual decisions live in CSS custom properties. The mechanism can stay stable while themes override size, color, radius, and hover states.
- **Reusable utility**: `.ui-scrollbar` applies the same scrollbar treatment to custom scrollable containers without coupling the rules to one component.
- **Native fallback**: Unsupported selectors or properties are ignored by the browser. The content remains scrollable even when styling support is limited.

## Current limitations

- **Limited standard API**: `scrollbar-color` and `scrollbar-width` only expose basic styling. Fine-grained parts like thumb hover, corner, and track details still rely on WebKit pseudo-elements.
- **Browser conflicts**: When supported standard properties are set to non-auto values, they can override `::-webkit-scrollbar` styling. Scope standard rules carefully to avoid conflicts.
- **Platform differences**: Overlay scrollbars, operating system settings, touch devices, and forced-colors modes can change or reduce the visible effect of custom scrollbar styling.

## Source

Full explanation and demo: <https://browui.com/native-browser-ui/scrollbar/>
