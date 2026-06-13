<div align="center">
  <img src="./../../assets/carousel.svg" alt="logo carousel" width="150"/>
  <h1>BrowUI Carousel</h1>
</div>

**A native carousel built with horizontal scrolling, `scroll-snap`, and progressive CSS controls.** Slides snap into place naturally, while supported browsers can add scroll buttons, markers, and active-slide styling without JavaScript.

## At a glance

- 0 KB JavaScript
- ~70 CSS lines
- native scroll snapping
- progressive controls

## Files

- `carousel.css`: CSS mechanisms and theme hooks from the component snippet.
- `carousel.html`: portable markup from the component snippet.

## Markup

```html
<div class="carousel" tabindex="0" aria-label="Carousel">
  <div class="slide" data-label="Slide 1">
    <div class="slide-inner"><!-- Slide content --></div>
  </div>
  <div class="slide origin" data-label="Slide 2">
    <div class="slide-inner"><!-- Slide content --></div>
  </div> 
  <div class="slide" data-label="Slide 3">
    <div class="slide-inner"><!-- Slide content --></div>
  </div> 
  <!-- Other slides -->
</div>
```

## CSS mechanisms

- Carousel Containers
- Carousel Slide
- Carousel Initial Position
- Carousel Buttons
- Carousel Markers
- Carousel Active slide

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Pagination dots | `::scroll-marker` | Experimental | 135+ | 135+ | - | - | [Can I Use](https://caniuse.com/wf-scroll-markers) |
| Prev / Next buttons | `::scroll-button()` | Experimental | 135+ | 135+ | - | - | [Can I Use](https://caniuse.com/mdn-css_selectors_scroll-button) |
| Active slide | `@container scroll-state()` | Experimental | 133+ | 133+ | - | - | [Can I Use](https://caniuse.com/wf-container-scroll-state-queries) |
| Initial position | `scroll-initial-target` | Experimental | 133+ | 133+ | - | - | [Can I Use](https://caniuse.com/wf-scroll-initial-target) |

## Benefits

- **A11y**: The browser generates sibling DOM elements with the appropriate ARIA roles, in the correct tab order, and maintains their state.
- **Performance**: Pure CSS carousels improve performance by eliminating JavaScript parsing and event listeners.
- **Progressive enhancement**: Snap scrolling works everywhere, markers add a richer UX where supported.

## Current limitations

- **Browser support**: `::scroll-button()`, `::scroll-marker`, `@container scroll-state()` and `scroll-initial-target` are available in Chrome and Edge. Can I Use currently lists no stable Firefox or Safari support for these features.
- **Cyclic scrolling**: One of the main limitations is the creation of a cyclical carousel, allowing the user to go directly from the last slide to the first.
- **Autoplay**: To add features like autoplay or start/stop controls, JavaScript is probably still necessary.
- **A11y**: Because inactive slides are not hidden via `display: none`, screen readers can announce all slides, even those not visible.

## Source

Full explanation and demo: <https://browui.com/ui-components/carousel/>
