<div align="center">
  <img src="./../../assets/switch.svg" alt="logo switch" width="150"/>
  <h1>BrowUI Switch</h1>
</div>

**A native switch built with a real `<input type="checkbox">`.** The label toggles the control, while CSS state hooks style the track and thumb from the checkbox state.

## At a glance

- 0 KB JavaScript
- ~30 CSS lines
- checkbox native state
- native keyboard access

## Files

- `switch.css`: CSS mechanisms and theme hooks from the component snippet.
- `switch.html`: portable markup from the component snippet.

## Markup

```html
<label class="switch">
  <input class="switch-input" type="checkbox" checked>
  <span class="switch-track" aria-hidden="true"></span>
  <span class="switch-label">Switch title</span>
</label>
```

## CSS mechanisms

- Switch Layout
- Switch Track & Thumb
- Switch State hooks

## Browser support

Support data is a June 2026 snapshot checked against Can I Use where the feature is tracked. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Native checkbox state | `<input type="checkbox" checked>` | Stable | All | All | All | All | [HTML Living Standard](https://html.spec.whatwg.org/multipage/input.html#checkbox-state-(type=checkbox)) |
| Parent state hook | `:has()` | Stable | 105+ | 105+ | 121+ | 15.4+ | [Can I Use](https://caniuse.com/css-has) |
| Keyboard focus hook | `:focus-visible` | Stable | 86+ | 86+ | 85+ | 15.4+ | [Can I Use](https://caniuse.com/css-focus-visible) |

## Benefits

- **Native control**: The real `<input>` keeps browser-managed checked state, form behavior, keyboard access, and change events.
- **Label activation**: Wrapping the input in a `<label>` makes the full switch row clickable without extra JavaScript.
- **CSS-only state**: The visual track and thumb react to `:checked`, `:focus-visible`, and `:has()` without runtime state.
- **Style agnostic**: The snippet only defines the mechanics. Size, colors, spacing, focus ring, and motion remain fully themeable.

## Current limitations

- **Switch semantics**: A checkbox behaves correctly, but may still be announced as a checkbox. Use dedicated switch semantics only when the project needs that exact assistive technology output.
- **Parent styling support**: Styling the parent depends on `:has()`. For older browsers, basic track and thumb states can still use `:checked + .switch-track`.
- **Hidden input care**: The checkbox must stay focusable and associated with its label. Avoid `display: none` or removing visible focus styles.

## Source

Full explanation and demo: <https://browui.com/ui-components/switch/>
