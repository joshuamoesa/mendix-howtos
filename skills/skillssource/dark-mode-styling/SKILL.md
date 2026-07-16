---
name: dark-mode-styling
description: Applies a comprehensive dark mode theme to Mendix apps using Atlas UI 3 SCSS variable overrides, inspired by shadcn/ui's pure-black dark palette. Use when styling any page, widget, or component for dark mode — covers backgrounds, typography, borders, navigation, buttons, forms, grids, tabs, modals, alerts, labels, groupbox, accordion, wizard, timeline, and dataview.
---

## Purpose

This skill defines a full dark mode color scheme for Mendix Atlas UI 3 apps, matching shadcn/ui's pure-black dark aesthetic. The base canvas is true black (`#000000`), cards and surfaces sit at near-black (`#09090b`), and borders are barely visible (`#18181b`). Primary buttons are inverted (white on black).

## Toggle Mechanism

Dark mode is controlled by a single SCSS variable at the top of `theme/web/custom-variables.scss`:

```scss
$dark-mode: true;   // Set to false to disable dark mode
```

All dark mode variable overrides and the `:root` block are wrapped in an `@if $dark-mode { }` conditional. When `$dark-mode` is `false`, no overrides are applied and Atlas falls back to its default light theme.

### Enabling dark mode

1. Set `$dark-mode: true;` at the top of `custom-variables.scss` (or add it if missing)
2. Ensure the `@if $dark-mode { ... }` block with all overrides exists below it

### Disabling dark mode

1. Set `$dark-mode: false;` — no other changes needed, the `@if` block is skipped entirely

### Checking current state

Read `custom-variables.scss` and look for `$dark-mode:`. If it is `true`, dark mode is active. If it is `false` or absent, dark mode is off.

## How to Apply

Override SCSS variables in `theme/web/custom-variables.scss`. Atlas uses `$variable-name` SCSS variables with `!default` flags, so any value you set in `custom-variables.scss` takes precedence over the core defaults.

Because `$use-css-variables: true` is set, Atlas resolves colours from CSS custom properties at runtime — SCSS `$variable` overrides alone are not enough. Always add a full `:root { }` block that mirrors every SCSS variable as a CSS custom property. Without it, Atlas's default `:root` values win and the theme appears grey.

Both the SCSS overrides and the `:root` block must be inside the `@if $dark-mode { }` conditional so they are only applied when dark mode is enabled.

Before writing: Always read the full `custom-variables.scss` file first. Identify the existing variable declarations and insert or replace them. Never delete unrelated variables or replace the entire file unless it is empty.


## Color Palette

| Role | Hex | Usage |
|---|---|---|
| Base background | `#000000` | Page canvas, deepest layer — true black |
| Elevated surface | `#09090b` | Cards, popovers, modals, grouped content |
| Subtle surface | `#0f0f11` | Hover states on cards, striped rows |
| Muted surface | `#18181b` | Secondary fills, disabled backgrounds, sub-navigation |
| Border | `#1c1c20` | Card borders, dividers, input borders — barely visible |
| Strong border | `#27272a` | Active borders, focus rings, emphasized dividers |
| Muted text | `#71717a` | Placeholders, disabled text, tertiary labels |
| Secondary text | `#a1a1aa` | Captions, descriptions, sub-labels |
| Body text | `#e4e4e7` | Default readable text, form labels |
| Heading text | `#fafafa` | Headers, high-emphasis text, primary button text |
| Primary accent | `#fafafa` | Primary buttons (inverted: white bg, black text) |
| Primary hover | `#e4e4e7` | Primary button hover |
| Secondary accent | `#27272a` | Secondary buttons background |
| Link color | `#60a5fa` | Hyperlinks, inline actions |
| Destructive | `#dc2626` | Danger buttons, error states |
| Success | `#22c55e` | Success alerts, labels |
| Warning | `#eab308` | Warning alerts, labels |

## SCSS Variable Mappings

Below are all Atlas SCSS variables grouped by category, with their dark mode values.

### Gray Shades

| Variable | Dark Value |
|---|---|
| `$gray-darker` | `#fafafa` |
| `$gray-dark` | `#a1a1aa` |
| `$gray` | `#71717a` |
| `$gray-light` | `#52525b` |
| `$gray-primary` | `#1c1c20` |
| `$gray-lighter` | `#09090b` |

### Brand Colors

| Variable | Dark Value |
|---|---|
| `$brand-default` | `#1c1c20` |
| `$brand-primary` | `#fafafa` |
| `$brand-success` | `#22c55e` |
| `$brand-warning` | `#eab308` |
| `$brand-danger` | `#dc2626` |

### Backgrounds

| Variable | Dark Value |
|---|---|
| `$bg-color` | `#000000` |
| `$bg-color-secondary` | `#09090b` |

### Typography

| Variable | Dark Value |
|---|---|
| `$font-color-default` | `#e4e4e7` |
| `$font-color-detail` | `#a1a1aa` |
| `$font-color-header` | `#fafafa` |

### Borders

| Variable | Dark Value |
|---|---|
| `$border-color-default` | `#1c1c20` |

### Links

| Variable | Dark Value |
|---|---|
| `$link-color` | `#60a5fa` |

### Navigation — Topbar

| Variable | Dark Value |
|---|---|
| `$topbar-bg` | `#000000` |
| `$topbar-border-color` | `#1c1c20` |
| `$navtopbar-bg` | `#000000` |
| `$navtopbar-bg-hover` | `#09090b` |
| `$navtopbar-bg-active` | `#09090b` |
| `$navtopbar-color` | `#e4e4e7` |
| `$navtopbar-color-hover` | `#fafafa` |
| `$navtopbar-color-active` | `#fafafa` |
| `$navtopbar-sub-bg` | `#09090b` |
| `$navtopbar-sub-bg-hover` | `#18181b` |
| `$navtopbar-sub-bg-active` | `#18181b` |
| `$navtopbar-sub-color` | `#a1a1aa` |
| `$navtopbar-sub-color-hover` | `#fafafa` |
| `$navtopbar-sub-color-active` | `#fafafa` |
| `$navtopbar-border-color` | `#1c1c20` |
| `$navbar-brand-name` | `#fafafa` |

### Navigation — Sidebar

| Variable | Dark Value |
|---|---|
| `$sidebar-bg` | `#000000` |
| `$navsidebar-bg` | `#000000` |
| `$navsidebar-bg-hover` | `#09090b` |
| `$navsidebar-bg-active` | `#09090b` |
| `$navsidebar-color` | `#e4e4e7` |
| `$navsidebar-color-hover` | `#fafafa` |
| `$navsidebar-color-active` | `#fafafa` |
| `$navsidebar-sub-bg` | `#09090b` |
| `$navsidebar-sub-bg-hover` | `#18181b` |
| `$navsidebar-sub-bg-active` | `#18181b` |
| `$navsidebar-sub-color` | `#a1a1aa` |
| `$navsidebar-sub-color-hover` | `#fafafa` |
| `$navsidebar-sub-color-active` | `#fafafa` |
| `$navsidebar-border-color` | `#1c1c20` |

### Navigation — Mobile Header

| Variable | Dark Value |
|---|---|
| `$m-header-bg` | `#000000` |
| `$m-header-color` | `#fafafa` |

### Forms & Inputs

| Variable | Dark Value |
|---|---|
| `$form-label-color` | `#e4e4e7` |
| `$form-input-bg` | `#09090b` |
| `$form-input-bg-focus` | `#09090b` |
| `$form-input-bg-hover` | `#0f0f11` |
| `$form-input-bg-disabled` | `#18181b` |
| `$form-input-color` | `#e4e4e7` |
| `$form-input-focus-color` | `#fafafa` |
| `$form-input-disabled-color` | `#52525b` |
| `$form-input-placeholder-color` | `#52525b` |
| `$form-input-border-color` | `#1c1c20` |
| `$form-input-border-focus-color` | `#27272a` |
| `$form-input-static-border-color` | `#1c1c20` |

### Buttons

Primary buttons use an **inverted** style: white background with black text, matching the shadcn/ui default dark button pattern.

| Variable | Dark Value |
|---|---|
| `$btn-default-bg` | `#09090b` |
| `$btn-default-border-color` | `#1c1c20` |
| `$btn-default-color` | `#e4e4e7` |
| `$btn-default-bg-hover` | `#18181b` |
| `$btn-default-icon-color` | `#a1a1aa` |
| `$btn-primary-bg` | `#fafafa` |
| `$btn-primary-border-color` | `#fafafa` |
| `$btn-primary-color` | `#09090b` |
| `$btn-primary-bg-hover` | `#e4e4e7` |
| `$btn-success-bg` | `#22c55e` |
| `$btn-success-border-color` | `#22c55e` |
| `$btn-success-color` | `#fafafa` |
| `$btn-success-bg-hover` | `#16a34a` |
| `$btn-warning-bg` | `#eab308` |
| `$btn-warning-border-color` | `#eab308` |
| `$btn-warning-color` | `#09090b` |
| `$btn-warning-bg-hover` | `#ca8a04` |
| `$btn-danger-bg` | `#dc2626` |
| `$btn-danger-border-color` | `#dc2626` |
| `$btn-danger-color` | `#fafafa` |
| `$btn-danger-bg-hover` | `#b91c1c` |
| `$btn-link-bg-hover` | `#09090b` |

### Cards & Shadows

| Variable | Dark Value |
|---|---|
| `$shadow-color-border` | `rgba(0, 0, 0, 0.5)` |
| `$shadow-color` | `rgba(0, 0, 0, 0.6)` |

### Grids & Data Tables

| Variable | Dark Value |
|---|---|
| `$grid-border-color` | `#1c1c20` |
| `$grid-bg` | `transparent` |
| `$grid-bg-header` | `#09090b` |
| `$grid-bg-hover` | `#0f0f11` |
| `$grid-bg-selected` | `#18181b` |
| `$grid-bg-selected-hover` | `#27272a` |
| `$grid-bg-striped` | `#050507` |
| `$grid-footer-bg` | `#09090b` |
| `$grid-selected-color` | `#fafafa` |
| `$grid-paging-color` | `#52525b` |
| `$grid-paging-color-hover` | `#fafafa` |

### Tabs

| Variable | Dark Value |
|---|---|
| `$tabs-color` | `#a1a1aa` |
| `$tabs-color-active` | `#fafafa` |
| `$tabs-lined-color-active` | `#fafafa` |
| `$tabs-border-color` | `#1c1c20` |
| `$tabs-lined-border-color` | `#fafafa` |
| `$tabs-bg` | `transparent` |
| `$tabs-bg-pills` | `#18181b` |
| `$tabs-bg-hover` | `#09090b` |
| `$tabs-bg-active` | `#fafafa` |

### Modals

| Variable | Dark Value |
|---|---|
| `$modal-header-bg` | `#09090b` |
| `$modal-header-border-color` | `#1c1c20` |
| `$modal-header-color` | `#fafafa` |

### Alerts

| Variable | Dark Value |
|---|---|
| `$alert-success-bg` | `#052e16` |
| `$alert-success-color` | `#86efac` |
| `$alert-success-border-color` | `#14532d` |
| `$alert-warning-bg` | `#422006` |
| `$alert-warning-color` | `#fde68a` |
| `$alert-warning-border-color` | `#713f12` |
| `$alert-danger-bg` | `#450a0a` |
| `$alert-danger-color` | `#fca5a5` |
| `$alert-danger-border-color` | `#7f1d1d` |

### Labels

| Variable | Dark Value |
|---|---|
| `$label-default-bg` | `#18181b` |
| `$label-default-border-color` | `#27272a` |
| `$label-default-color` | `#e4e4e7` |
| `$label-primary-color` | `#09090b` |
| `$label-success-color` | `#fafafa` |
| `$label-warning-color` | `#09090b` |
| `$label-danger-color` | `#fafafa` |

### Groupbox

| Variable | Dark Value |
|---|---|
| `$groupbox-default-bg` | `#09090b` |
| `$groupbox-default-color` | `#e4e4e7` |
| `$groupbox-primary-color` | `#09090b` |
| `$groupbox-success-color` | `#fafafa` |
| `$groupbox-warning-color` | `#09090b` |
| `$groupbox-danger-color` | `#fafafa` |
| `$groupbox-white-bg` | `#09090b` |
| `$groupbox-white-color` | `#e4e4e7` |

### Callout

| Variable | Dark Value |
|---|---|
| `$callout-default-color` | `#e4e4e7` |
| `$callout-default-bg` | `#09090b` |
| `$callout-success-bg` | `#052e16` |
| `$callout-warning-bg` | `#422006` |
| `$callout-danger-bg` | `#450a0a` |

### Accordion

| Variable | Dark Value |
|---|---|
| `$accordion-header-default-bg` | `#09090b` |
| `$accordion-header-default-bg-hover` | `#0f0f11` |
| `$accordion-header-default-color` | `#fafafa` |
| `$accordion-default-border-color` | `#1c1c20` |
| `$accordion-bg-striped` | `#050507` |
| `$accordion-bg-striped-hover` | `#0f0f11` |

### Wizard

| Variable | Dark Value |
|---|---|
| `$wizard-default-bg` | `#09090b` |
| `$wizard-default-color` | `#e4e4e7` |
| `$wizard-default-step-color` | `#71717a` |
| `$wizard-default-border-color` | `#1c1c20` |

### Timeline

| Variable | Dark Value |
|---|---|
| `$timeline-border-color` | `#1c1c20` |
| `$timeline-grouping-border-color` | `#1c1c20` |

### Dataview

| Variable | Dark Value |
|---|---|
| `$dataview-controls-bg` | `#09090b` |
| `$dataview-controls-border-color` | `#1c1c20` |
| `$dataview-emptymessage-bg` | `#000000` |
| `$dataview-emptymessage-color` | `#71717a` |

### Header Blocks

| Variable | Dark Value |
|---|---|
| `$header-bg-color` | `#000000` |
| `$header-text-color` | `#fafafa` |
| `$header-text-color-detail` | `rgba(255, 255, 255, 0.3)` |

### Underlay

The `.mx-underlay` (modal backdrop) should use `rgba(0, 0, 0, 0.8)` for dark mode contrast.

See [variable-overrides](references/variable-overrides.md) for the complete copy-paste SCSS block.
