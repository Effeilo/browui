<div align="center">
  <img src="./../../assets/tabs.svg" alt="logo tabs" width="150"/>
  <h1>BrowUI Tabs</h1>
</div>

**This is a CSS-only radio-driven tab switcher.** It uses native radio semantics, so assistive technologies expose it as a radio group rather than as ARIA tabs.

## At a glance

- 0 KB JavaScript
- ~60 CSS lines
- radio-driven state
- native radio keyboard

## Files

- `tabs.css`: CSS mechanisms and theme hooks from the component snippet.
- `tabs.html`: portable markup from the component snippet.

## Markup

```html
<fieldset class="tabs">
  <legend class="sr-only">Choose which panel to display</legend>

  <input type="radio" name="example-tabs" id="example-tab-1" checked>
  <input type="radio" name="example-tabs" id="example-tab-2">
  <input type="radio" name="example-tabs" id="example-tab-3">

  <div class="tab-list">
    <label id="example-tab-label-1" for="example-tab-1" class="tab-label">...</label>
    <label id="example-tab-label-2" for="example-tab-2" class="tab-label">...</label>
    <label id="example-tab-label-3" for="example-tab-3" class="tab-label">...</label>
  </div>

  <div class="tab-panels">
    <div class="tab-panel" data-tab="1" aria-labelledby="example-tab-label-1">...</div>
    <div class="tab-panel" data-tab="2" aria-labelledby="example-tab-label-2">...</div>
    <div class="tab-panel" data-tab="3" aria-labelledby="example-tab-label-3">...</div>
  </div>
</fieldset>
```

## CSS mechanisms

- Tabs Container
- Tab List & Labels
- :has() Driven State
- Tab Panels
- Tabs A11y

## Browser support

Support data is a June 2026 snapshot checked against Can I Use where the feature is tracked. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Native selection | `<input type="radio"> + <label>` | Stable | All | All | All | All | [HTML Living Standard](https://html.spec.whatwg.org/multipage/input.html#radio-button-state-(type=radio)) |
| CSS state routing | `:has(:checked)` | Stable | 105+ | 105+ | 121+ | 15.4+ | [Can I Use](https://caniuse.com/css-has) |
| Panel transition | `transition-behavior: allow-discrete` | Recent | 117+ | 117+ | 129+ | 17.4+ | [Can I Use](https://caniuse.com/mdn-css_properties_transition-behavior) |

## Benefits

- **Native state**: Radio inputs provide the exclusive selection model: only one panel can be active at a time, without JavaScript.
- **A11y baseline**: `<fieldset>`, `<legend>`, radios, and labels create a usable native control group with keyboard support and accessible names.
- **No state sync**: The checked radio is the source of truth. CSS reads it with `:has()`, so there is no duplicated JS state to maintain.
- **Content stays in HTML**: All panels remain in the document structure. The component stays readable without JavaScript and easy to progressively style.

## Current limitations

- **Not true ARIA tabs**: Assistive technologies expose this as a radio group, not as `tablist`, `tab`, and `tabpanel`. Do not add ARIA tab roles unless JavaScript keeps the states in sync.
- **Keyboard model**: Keyboard behavior follows native radio controls. It does not provide the full tabs pattern: roving focus, `Home`/`End`, manual activation, or panel focus management.
- **Static mapping**: Each tab needs matching IDs, labels, panels, and `:has()` selectors. This is fine for small examples, but verbose for dynamic or reusable components.
- **No native tabs API**: HTML still has no built-in tabs element. CSS cannot update `aria-selected`, `tabindex`, URL history, deep links, closable tabs, or lazy-loaded panels by itself.

## Source

Full explanation and demo: <https://browui.com/ui-components/tabs/>
