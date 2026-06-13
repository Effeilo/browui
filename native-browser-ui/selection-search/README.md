<div align="center">
  <img src="./../../assets/selection-search.svg" alt="logo Selection & search" width="150"/>
  <h1>BrowUI Selection & search</h1>
</div>

Native text highlights styled through CSS highlight pseudo-elements. The tokens keep the colors themeable, while `:root::selection` and `:root::search-text` preserve the browser's highlight inheritance model.

## At a glance

- 0 KB JavaScript
- 34 CSS lines
- native UX
- native fallback

## Files

- `selection-search.css`: CSS mechanisms and theme hooks from the component snippet.

## CSS mechanisms

- Native Highlight Tokens
- Text Selection
- Find-in-Page Highlight

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Text selection | `:root::selection` | Stable | 4+ | 12+ | 2+ | 3.1+ | [Can I Use](https://caniuse.com/css-selection) |
| Find-in-page matches | `:root::search-text` | Experimental | 144+ | 144+ | - | - | [Can I Use](https://caniuse.com/mdn-css_selectors_search-text) |
| Current search match | `:root::search-text:current` | Experimental | 144+ | 144+ | - | - | [Can I Use](https://caniuse.com/mdn-css_selectors_search-text) |

## Benefits

- **Native behavior**: The browser keeps handling text selection and find-in-page results. No JavaScript, no custom ranges, no duplicated search UI.
- **Themeable tokens**: Colors are exposed as custom properties, so the mechanism stays stable while each theme can define its own contrast pair.
- **Clean inheritance**: Using `:root` preserves the special inheritance model of CSS highlight pseudo-elements and keeps descendant overrides predictable.
- **Native fallback**: Unsupported browsers ignore `::search-text` and keep their native find-in-page highlight unchanged.

## Current limitations

- **Experimental search styling**: `::search-text` is still experimental and currently limited to Chromium-based browsers.
- **Restricted properties**: Highlight pseudo-elements only accept paint-related properties such as `color`, `background-color`, `text-decoration`, and `text-shadow`.
- **Contrast responsibility**: Always define foreground and background colors together. A single custom color can break contrast against browser defaults.

## Source

Full explanation and demo: <https://browui.com/native-browser-ui/selection/>
