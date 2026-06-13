<div align="center">
  <img src="./../../assets/accordion.svg" alt="logo accordion" width="150"/>
  <h1>BrowUI Accordion</h1>
</div>

**A native accordion built with `<details>` and `<summary>`.** The shared `name` attribute makes the group exclusive, so opening one panel closes the others.

## At a glance

- 0 KB JavaScript
- ~30 CSS lines
- exclusive details group
- native keyboard access

## Files

- `accordion.css`: CSS mechanisms and theme hooks from the component snippet.
- `accordion.html`: portable markup from the component snippet.

## Markup

```html
<div class="accordion">
  <details name="accordion-1" open>
    <summary>
      <!-- Section 1 -->
      <span class="chev" aria-hidden="true">+</span>
    </summary>
    <!-- Content 1 -->
  </details>  
  <details name="accordion-1">
    <summary>
      <!-- Section 2 -->
      <span class="chev" aria-hidden="true">+</span>
    </summary>
    <!-- Content 2 -->
  </details>  
  <!-- Other details -->
</div>
```

## CSS mechanisms

- Details
- Summary
- Chevron
- Open/Close Animation

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Exclusive accordion | `<details> name` | Recent | 120+ | 120+ | 130+ | 17.2+ | [Can I Use](https://caniuse.com/mdn-html_elements_details_name) |
| Details content wrapper | `::details-content` | Recent | 131+ | 131+ | 143+ | 18.4+ | [Can I Use](https://caniuse.com/mdn-css_selectors_details-content) |
| Intrinsic size interpolation | `interpolate-size` | Experimental | 129+ | 129+ | - | - | [Can I Use](https://caniuse.com/mdn-css_properties_interpolate-size) |

## Benefits

- **Semantic markup**: Clear structure: `<details>` contains one `<summary>` followed by flow content. Readable without CSS.
- **Native behavior**: The browser handles toggling, keyboard activation, focus, and open/closed state without manual ARIA.
- **Low runtime cost**: No JavaScript state, no hydration, no re-rendering. The disclosure behavior is handled by the platform.
- **DOM content**: Panel content remains in the document, available to search, indexing, copy/paste, and find-in-page.

## Current limitations

- **Animation support**: Smooth height animation depends on `::details-content` and `interpolate-size`. Without both, the accordion still works but falls back to an instant toggle.
- **Marker styling**: The native marker can be customized with `::marker`, but cross-browser cleanup still often requires `::-webkit-details-marker`.
- **Assistive tech differences**: Screen readers may announce summaries and state changes differently. Keep `<summary>` simple and test real combinations before adding ARIA.

## Source

Full explanation and demo: <https://browui.com/ui-components/accordion/>
