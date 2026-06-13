<div align="center">
  <img src="./../../assets/form.svg" alt="logo form" width="150"/>
  <h1>Form UX</h1>
</div>

**Native form controls enhanced with semantic theme tokens.** The snippet keeps browser UI behavior intact while exposing accent, caret, placeholder, validation, progress, and range states for customization.

## At a glance

- 0 KB JavaScript
- ~50 CSS lines
- browser-managed logic
- native fallback

## Files

- `form.css`: CSS mechanisms and theme hooks from the component snippet.

## CSS mechanisms

- Form Theme Tokens
- Accent Color
- Placeholder
- Caret Color
- Form Validation States
- Progress Bar

## Browser support

Support data is a June 2026 snapshot checked against Can I Use. Treat it as a platform note, not a compatibility guarantee.

| Feature | API | Status | Chrome | Edge | Firefox | Safari | Reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Native accent color | `accent-color` | Partial | 93+ | 93+ | 92+ | 15.4+ partial / 26.2+ full | [Can I Use](https://caniuse.com/mdn-css_properties_accent-color) |
| User validation states | `:user-valid` / `:user-invalid` | Stable | 119+ | 119+ | 88+ | 16.5+ | [Can I Use](https://caniuse.com/wf-user-pseudos) |
| Editing and hint tokens | `caret-color` / `::placeholder` | Stable | 57+ | 79+ | 53+ | 11.1+ | [Can I Use](https://caniuse.com/css-caret-color), [Can I Use](https://caniuse.com/css-placeholder) |

## Benefits

- **Native controls**: Browser form controls keep their built-in behavior, platform conventions, keyboard handling, and focus model.
- **Semantic theming**: Customization is exposed through form-specific tokens, so themes can adapt the UI without replacing native controls.
- **Better feedback timing**: `:user-valid` and `:user-invalid` avoid showing validation styles before the user interacts with a field.
- **No runtime cost**: No JavaScript state, no hydration, and no custom widget logic. The browser remains responsible for the interaction.

## Current limitations

- **Browser-owned rendering**: Native controls are still rendered by the browser and operating system. The same token may produce slightly different results across platforms.
- **Partial accent coverage**: `accent-color` is most consistent on checkboxes, radios, ranges, and progress. `<meter>` and `<select>` remain progressive enhancements.
- **Vendor pseudo-elements**: Progress and range internals still rely on browser-specific pseudo-elements. Full custom tracks and thumbs belong in a component layer.

## Source

Full explanation and demo: <https://browui.com/native-browser-ui/form/>
