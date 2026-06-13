<div align="center">
  <img src="./../../assets/modal.svg" alt="logo modal" width="150"/>
  <h1>BrowUI Modal</h1>
</div>

A native modal built with `<dialog>` and declarative `command` buttons. The browser handles the top layer, focus behavior, modal state, and closing actions without custom JavaScript.

## At a glance

- 0 KB JavaScript
- ~40 CSS lines
- declarative command controls
- native modal behavior

## Files

- `modal.css`: CSS mechanisms and theme hooks from the component snippet.
- `modal.html`: portable markup from the component snippet.

## Markup

```html
<button type="button" commandfor="native-dialog" command="show-modal">
  Open modal
</button>

<dialog id="native-dialog" class="modal" aria-labelledby="modal-title">
  <div class="modal-inner">
    <button class="modal-close" type="button" commandfor="native-dialog" command="request-close" aria-label="Close">&times;</button>

    <h2 id="modal-title">Modal title</h2>

    <!-- content -->

    <button type="button" commandfor="native-dialog" command="close" value="cancel">Cancel</button>
    <button type="button" commandfor="native-dialog" command="close" value="ok">OK</button>
  </div>
</dialog>
```

## CSS mechanisms

- Modal
- Modal close button
- Modal Animation (Top Layer)

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Native modal element | `<dialog>` | Stable | 37+ | 79+ | 98+ | 15.4+ | [Can I Use](https://caniuse.com/dialog) |
| Declarative commands | `commandfor` + `command` | Recent | 135+ | 135+ | 144+ | 26.2+ | [Can I Use](https://caniuse.com/mdn-html_elements_button_commandfor) |
| Top-layer transitions | `@starting-style` + `allow-discrete` | Recent | 117+ | 117+ | 129+ | 17.4+ | [Can I Use](https://caniuse.com/mdn-css_properties_transition-behavior), [Can I Use](https://caniuse.com/mdn-css_at-rules_starting-style) |

## Benefits

- **Semantic markup**: Purpose-built modal structure with `<dialog>`, explicit controls, and accessible labelling via `aria-labelledby`.
- **Native modal behavior**: The browser handles the top layer, backdrop, focus behavior, inert page content, and `Esc` dismissal.
- **No custom JavaScript**: Buttons can open and close the modal declaratively with `commandfor` and `command`.
- **Return values**: Closing buttons can pass a result with `value`, exposed through the dialog's native `returnValue`.

## Current limitations

- **Command support**: `commandfor` is newer than `<dialog>`. Without it, the modal element still exists, but declarative open and close buttons need a fallback.
- **Animation support**: Smooth entry and exit transitions depend on `@starting-style`, `allow-discrete`, `display`, and `overlay`. Without them, the modal still works but may appear or disappear instantly.
- **Focus decisions**: The browser provides modal focus behavior, but authors still need to choose sensible labels, close controls, and optional `autofocus` placement.

## Source

Full explanation and demo: <https://browui.com/ui-components/modal/>
