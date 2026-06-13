<div align="center">
  <img src="./../../assets/tooltip.svg" alt="logo tooltip" width="150"/>
  <h1>BrowUI Tooltip</h1>
</div>

**A CSS-only tooltip anchored with `anchor-name` and `position-anchor`.** The tooltip is revealed on hover or focus, with a classic absolute-positioning fallback for unsupported browsers.

## At a glance

- 0 KB JavaScript
- ~30 CSS lines
- anchor-positioned tooltip
- hover and focus reveal

## Files

- `tooltip.css`: CSS mechanisms and theme hooks from the component snippet.
- `tooltip.html`: portable markup from the component snippet.

## Markup

```html
<span class="anchor anchor-1" tabindex="0" aria-describedby="tooltip-1">
  Anchor
  <span id="tooltip-1" class="tooltip tooltip-1" role="tooltip">Tooltip text.</span>
</span>
```

## CSS mechanisms

- Anchor
- Tooltip Box
- Anchor Positioning Override

## Browser support

Support data is a June 2026 snapshot checked against Can I Use where the feature is tracked. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Anchor positioning | `anchor-name / position-anchor / anchor()` | Recent | 125+ | 125+ | 147+ | 26+ | [Can I Use](https://caniuse.com/css-anchor-positioning) |
| Feature query fallback | `@supports` | Stable | 28+ | 12+ | 22+ | 9+ | [Can I Use](https://caniuse.com/css-featurequeries) |
| Accessible description | `aria-describedby / role="tooltip"` | Stable | Yes | Yes | Yes | Yes | [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/patterns/tooltip/) |

## Benefits

- **No JavaScript state**: The tooltip is revealed with CSS using `:hover`, `:focus`, and `:focus-within`. No event listeners, no runtime state, no hydration.
- **Keyboard reachable**: The anchor can receive focus with `tabindex="0"`, so keyboard users can reveal the tooltip without relying on hover.
- **Precise positioning**: `anchor-name` and `position-anchor` let the tooltip position itself from the anchor's real coordinates instead of depending only on parent-relative offsets.
- **Progressive fallback**: Unsupported browsers still get a classic absolute-positioning fallback. The tooltip remains usable, even without CSS Anchor Positioning.

## Current limitations

- **Anchor declarations**: Each tooltip needs a unique anchor name, such as `--a1`, and a matching `position-anchor`. This makes the association explicit but adds per-tooltip CSS.
- **Browser support**: CSS Anchor Positioning is still progressive enhancement. Use `@supports` and keep a fallback for browsers that do not support `anchor-name` yet.
- **Accessibility limits**: Use `aria-describedby` and `role="tooltip"` when appropriate, but keep tooltip content short. Complex interactive content should use another pattern.

## Source

Full explanation and demo: <https://browui.com/ui-components/tooltip/>
