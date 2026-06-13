<div align="center">
  <img src="./../../assets/progress-bar.svg" alt="logo progress bar" width="150"/>
  <h1>BrowUI Progress Bar</h1>
</div>

**A native scroll progress indicator powered by CSS scroll-driven animations.** The bar tracks the root scroll timeline and grows from left to right without JavaScript.

## At a glance

- 0 KB JavaScript
- ~20 CSS lines
- scroll() timeline
- fixed page indicator

## Files

- `progress-bar.css`: CSS mechanisms and theme hooks from the component snippet.
- `progress-bar.html`: portable markup from the component snippet.

## Markup

```html
<div class="scroll-progress" aria-hidden="true"></div>
```

## CSS mechanisms

- Scroll progress bar

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Scroll timeline | `animation-timeline: scroll(root block)` | Experimental | 115+ | 115+ | Disabled by default | 26+ | [Can I Use](https://caniuse.com/mdn-css_properties_animation-timeline_scroll) |
| Transform growth | `@keyframes / transform: scaleX()` | Stable | 4+ | 12+ | 5+ | 5.1+ | [Can I Use](https://caniuse.com/css-animation), [Can I Use](https://caniuse.com/transforms2d) |
| Feature query | `@supports` | Stable | 28+ | 12+ | 22+ | 9+ | [Can I Use](https://caniuse.com/css-featurequeries) |

## Benefits

- **No scroll listener**: The progress value is driven by the browser's scroll timeline. No JavaScript, no scroll events, no manual percentage calculation.
- **Minimal markup**: The component only needs one decorative element. The page content does not need to be wrapped or restructured.
- **Transform based**: The bar grows with `scaleX()`, so the animation avoids layout changes while still reflecting the scroll position.
- **CSS fallback**: Unsupported browsers can simply skip the indicator. The page remains fully usable because the bar is only a visual helper.

## Current limitations

- **Browser support**: Scroll-driven animations are still progressive enhancement because Firefox currently requires a browser flag for `animation-timeline`.
- **Decorative status**: Without JavaScript, the bar cannot expose a live `aria-valuenow`. Mark it with `aria-hidden="true"` and keep it visual only.
- **Root scroll only**: `scroll(root block)` tracks the page viewport. For a nested scroll area, use another scroller value or a named scroll timeline.

## Source

Full explanation and demo: <https://browui.com/ui-components/progress-bar/>
