<div align="center">
  <img src="./../../assets/focus.svg" alt="logo focus" width="150"/>
  <h1>Focus Management</h1>
</div>

**A native focus system built with `:focus` and `:focus-visible`.** The custom properties define the indicator, while the browser decides when focus should be visible.

## At a glance

- 0 KB JavaScript
- 16 CSS lines
- browser-managed logic
- native fallback

## Files

- `focus.css`: CSS mechanisms and theme hooks from the component snippet.

## CSS mechanisms

- Focus Variables
- Focus Management

## Browser support

Support data is a June 2026 snapshot checked against Can I Use where the feature is tracked. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Focus fallback | `:focus` | Stable | All | All | All | All | [Selectors Level 4](https://drafts.csswg.org/selectors/#the-focus-pseudo) |
| Visible focus heuristic | `:focus-visible` | Stable | 86+ | 86+ | 85+ | 15.4+ | [Can I Use](https://caniuse.com/css-focus-visible) |
| Low specificity target | `:where()` | Stable | 88+ | 88+ | 78+ | 14+ | [Can I Use](https://caniuse.com/mdn-css_selectors_where) |

## Benefits

- **Accessible fallback**: Focused interactive elements keep a visible indicator even before `:focus-visible` refinement is applied.
- **Native behavior**: The browser handles focus visibility heuristics across keyboard, pointer, touch, and script-driven focus changes.
- **Theme friendly**: The ring width, color, and offset are controlled through custom properties rather than duplicated in each rule.
- **Easy overrides**: The selector remains intentionally light, so components can replace or refine the focus style without fighting specificity.

## Current limitations

- **Browser logic**: `:focus-visible` depends on user-agent logic. Text inputs, script focus, and pointer focus may be treated differently across browsers.
- **Focusable markup**: The rules only help elements that can receive focus. Disabled controls, links without `href`, and unmanaged custom widgets still need correct markup.
- **Contrast responsibility**: The mechanism exposes the indicator, but the chosen `--focus-color`, width, and offset still need to remain visible in every theme.

## Source

Full explanation and demo: <https://browui.com/native-browser-ui/focus/>
