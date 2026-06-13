<div align="center">
  <img src="./../../assets/popover.svg" alt="logo popover" width="150"/>
  <h1>BrowUI Popover</h1>
</div>

**A native popover built with the `popover` attribute and declarative `popovertarget` buttons.** The browser handles the top layer, light dismiss, Escape closing, and open state without custom JavaScript.

## At a glance

- 0 KB JavaScript
- ~40 CSS lines
- declarative popover controls
- native light dismiss

## Files

- `popover.css`: CSS mechanisms and theme hooks from the component snippet.
- `popover.html`: portable markup from the component snippet.

## Markup

```html
<button type="button" popovertarget="info-popover">
  Open popover
</button>

<div id="info-popover" popover="auto" class="popover" aria-labelledby="popover-title">
  <div class="popover-inner">
    <button class="popover-close" type="button" popovertarget="info-popover" popovertargetaction="hide" aria-label="Close">&times;</button>

    <h2 id="popover-title">Contextual popover</h2>

    <!-- content -->

    <button type="button" popovertarget="info-popover" popovertargetaction="hide">Got it</button>
  </div>
</div>
```

## CSS mechanisms

- Popover
- Popover close button
- Popover Animation (Top Layer)

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Native popover element | `popover="auto"` | Stable | 114+ | 114+ | 125+ | 17+ | [Can I Use](https://caniuse.com/mdn-api_htmlelement_popover) |
| Declarative controls | `popovertarget` + `popovertargetaction` | Stable | 114+ | 114+ | 125+ | 17+ | [Can I Use](https://caniuse.com/mdn-html_elements_button_popovertarget) |
| Discrete transitions | `@starting-style` + `allow-discrete` | Recent | 117+ | 117+ | 129+ | 17.4+ | [Can I Use](https://caniuse.com/mdn-css_properties_transition-behavior), [Can I Use](https://caniuse.com/mdn-css_at-rules_starting-style) |

## Benefits

- **Declarative markup**: The relationship between the button and panel is declared in HTML with `popovertarget`. No custom click handler is needed.
- **Native top layer**: The browser places the popover above the page content, avoiding manual `z-index` stacking and portal-style workarounds.
- **Light dismiss**: With `popover="auto"`, the panel can close on outside click or `Esc`, using built-in browser behavior.
- **Low runtime cost**: No JavaScript state, no hydration, no re-rendering. Opening, closing, and visible state are handled by the platform.

## Current limitations

- **Non-modal behavior**: Popovers do not make the rest of the page inert. For blocking flows, confirmations, or required decisions, use a native `<dialog>`.
- **Positioning control**: The basic popover API handles visibility, not advanced placement. Anchored positioning may require newer CSS or a custom layout strategy.
- **Exit animation support**: Smooth top-layer exit depends on `overlay` with `allow-discrete`. Without full support, the popover still works but may close instantly.

## Source

Full explanation and demo: <https://browui.com/ui-components/popover/>
