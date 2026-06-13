<div align="center">
  <img src="./assets/logo-browui.svg" alt="BrowUI logo" width="150"/>
  <h1>Changelog</h1>
</div>

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)  
and this project adheres to [Semantic Versioning (SemVer)](https://semver.org/).

---

<br>

## [1.0.0] - 2026-06-13

Initial public release of BrowUI.

### Added

- Added the core BrowUI repository structure for copy-paste friendly native HTML and CSS interface patterns.
- Added eight user interface component patterns:
  - Carousel, built with native horizontal scrolling, `scroll-snap`, `::scroll-button`, `::scroll-marker`, `scroll-initial-target`, and scroll-state container queries.
  - Modal, built with `<dialog>` and declarative `commandfor` / `command` controls.
  - Popover, built with the Popover API, `popovertarget`, native light dismiss, and top-layer behavior.
  - Accordion, built with `<details>`, `<summary>`, and the `name` attribute for exclusive disclosure groups.
  - Tabs, built with native radio inputs, labels, `:checked`, and `:has()`.
  - Tooltip, built with CSS hover/focus reveal, `aria-describedby`, `role="tooltip"`, and CSS anchor positioning.
  - Progress bar, built with CSS scroll-driven animations and `animation-timeline`.
  - Switch, built with a real checkbox, label activation, `:checked`, `:focus-visible`, and `:has()`.
- Added four native browser UI patterns:
  - Selection and search highlights with `::selection`, `::search-text`, and `::search-text:current`.
  - Themed scrollbars with standard scrollbar properties and engine-scoped pseudo-elements.
  - Focus management with `:focus-visible`.
  - Form UX with `accent-color`, `caret-color`, `::placeholder`, `:user-valid`, and `:user-invalid`.
- Added SVG assets for each component and browser UI pattern.
- Added per-pattern README files with markup, CSS mechanisms, browser support notes, benefits, limitations, and source links.
- Added portable HTML and CSS source files for each component pattern.
- Added repository-level documentation describing BrowUI's principles, scope, browser support expectations, and contribution guidelines.
- Added project license.

### Documentation

- Documented BrowUI as a standards-first pattern collection rather than a component library, design system, framework, or compatibility layer.
- Clarified that BrowUI documents what modern HTML and CSS can do natively, including where browser support or accessibility semantics still require JavaScript in production systems.
- Added explicit browser support tables for modern platform features used across the examples.
- Added current limitations sections to make progressive enhancement boundaries visible for each pattern.

### Notes

- BrowUI intentionally ships no component JavaScript, build setup, runtime dependency, theme preset, or packaged API.
- Some examples rely on recent or experimental platform features. Unsupported browsers should keep the underlying content usable, but richer interactions may require browser support, fallbacks, or JavaScript in production systems.
