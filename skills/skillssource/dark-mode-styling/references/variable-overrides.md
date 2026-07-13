# Dark Mode SCSS Variable Overrides (Pure Black)

Copy and paste this block into `theme/web/custom-variables.scss`, replacing any existing values for the same variables.

> **IMPORTANT — CSS variables:** Because `$use-css-variables: true` is set in Atlas, SCSS `$variable` overrides alone are not enough. Atlas resolves colours from CSS custom properties at runtime, so the default `:root` values win otherwise (causing a grey appearance). Always accompany the SCSS block below with a full `:root { }` block that mirrors every variable as a CSS custom property. See the `:root` block at the bottom of this file.

> **Border colour:** All borders use `rgba(255, 255, 255, 0.15)` — white at 15% opacity — matching the shadcn/ui dark mode `--input` token (`oklch(1 0 0 / 15%)`). This gives the characteristic subtle grey-ish border on a black surface.

```scss
// ============================================================
// DARK MODE THEME — Pure black, shadcn/ui inspired
// Base: #000000 | Surface: #09090b | Border: rgba(255,255,255,0.15)
// Primary buttons are inverted (white bg, black text)
// ============================================================

//== Gray Shades (inverted for dark mode)
$gray-darker: #fafafa;
$gray-dark: #a1a1aa;
$gray: #71717a;
$gray-light: #52525b;
$gray-primary: #1c1c20;
$gray-lighter: #09090b;

//== Brand Colors
$brand-default: #1c1c20;
$brand-primary: #fafafa;
$brand-success: #22c55e;
$brand-warning: #eab308;
$brand-danger: #dc2626;

//== Backgrounds
$bg-color: #000000;
$bg-color-secondary: #09090b;

//== Typography
$font-color-default: #e4e4e7;
$font-color-detail: #a1a1aa;
$font-color-header: #fafafa;

//== Borders — white 15% opacity (shadcn/ui dark input border)
$border-color-default: rgba(255, 255, 255, 0.15);

//== Links
$link-color: #60a5fa;

//== Topbar
$topbar-bg: #000000;
$topbar-border-color: rgba(255, 255, 255, 0.15);
$navbar-brand-name: #fafafa;

//== Mobile Header
$m-header-bg: #000000;
$m-header-color: #fafafa;

//== Sidebar
$sidebar-bg: #000000;

//== Navigation — Sidebar
$navsidebar-bg: #000000;
$navsidebar-bg-hover: #09090b;
$navsidebar-bg-active: #09090b;
$navsidebar-color: #e4e4e7;
$navsidebar-color-hover: #fafafa;
$navsidebar-color-active: #fafafa;
$navsidebar-sub-bg: #09090b;
$navsidebar-sub-bg-hover: #18181b;
$navsidebar-sub-bg-active: #18181b;
$navsidebar-sub-color: #a1a1aa;
$navsidebar-sub-color-hover: #fafafa;
$navsidebar-sub-color-active: #fafafa;
$navsidebar-border-color: rgba(255, 255, 255, 0.15);

//== Navigation — Topbar
$navtopbar-bg: #000000;
$navtopbar-bg-hover: #09090b;
$navtopbar-bg-active: #09090b;
$navtopbar-color: #e4e4e7;
$navtopbar-color-hover: #fafafa;
$navtopbar-color-active: #fafafa;
$navtopbar-sub-bg: #09090b;
$navtopbar-sub-bg-hover: #18181b;
$navtopbar-sub-bg-active: #18181b;
$navtopbar-sub-color: #a1a1aa;
$navtopbar-sub-color-hover: #fafafa;
$navtopbar-sub-color-active: #fafafa;
$navtopbar-border-color: rgba(255, 255, 255, 0.15);

//== Forms & Inputs
$form-label-color: #e4e4e7;
$form-input-bg: #09090b;
$form-input-bg-focus: #09090b;
$form-input-bg-hover: #0f0f11;
$form-input-bg-disabled: #18181b;
$form-input-color: #e4e4e7;
$form-input-focus-color: #fafafa;
$form-input-disabled-color: #52525b;
$form-input-placeholder-color: #52525b;
$form-input-border-color: rgba(255, 255, 255, 0.15);
$form-input-border-focus-color: rgba(255, 255, 255, 0.35);
$form-input-static-border-color: rgba(255, 255, 255, 0.15);

//== Buttons — Default (outline style)
$btn-default-bg: #09090b;
$btn-default-border-color: rgba(255, 255, 255, 0.15);
$btn-default-color: #e4e4e7;
$btn-default-bg-hover: #18181b;
$btn-default-icon-color: #a1a1aa;

//== Buttons — Primary (inverted: white on black)
$btn-primary-bg: #fafafa;
$btn-primary-border-color: #fafafa;
$btn-primary-color: #09090b;
$btn-primary-bg-hover: #e4e4e7;

//== Buttons — Success
$btn-success-bg: #22c55e;
$btn-success-border-color: #22c55e;
$btn-success-color: #fafafa;
$btn-success-bg-hover: #16a34a;

//== Buttons — Warning
$btn-warning-bg: #eab308;
$btn-warning-border-color: #eab308;
$btn-warning-color: #09090b;
$btn-warning-bg-hover: #ca8a04;

//== Buttons — Danger
$btn-danger-bg: #dc2626;
$btn-danger-border-color: #dc2626;
$btn-danger-color: #fafafa;
$btn-danger-bg-hover: #b91c1c;

//== Buttons — Link
$btn-link-bg-hover: #09090b;

//== Cards & Shadows
$shadow-color-border: rgba(0, 0, 0, 0.5);
$shadow-color: rgba(0, 0, 0, 0.6);

//== Header Blocks
$header-bg-color: #000000;
$header-text-color: #fafafa;
$header-text-color-detail: rgba(255, 255, 255, 0.3);

//== Grids & Data Tables
$grid-border-color: rgba(255, 255, 255, 0.15);
$grid-bg: transparent;
$grid-bg-header: #09090b;
$grid-bg-hover: #0f0f11;
$grid-bg-selected: #18181b;
$grid-bg-selected-hover: #27272a;
$grid-bg-striped: #050507;
$grid-footer-bg: #09090b;
$grid-selected-color: #fafafa;
$grid-paging-color: #52525b;
$grid-paging-color-hover: #fafafa;

//== Tabs
$tabs-color: #a1a1aa;
$tabs-color-active: #fafafa;
$tabs-lined-color-active: #fafafa;
$tabs-border-color: rgba(255, 255, 255, 0.15);
$tabs-lined-border-color: #fafafa;
$tabs-bg: transparent;
$tabs-bg-pills: #18181b;
$tabs-bg-hover: #09090b;
$tabs-bg-active: #fafafa;

//== Modals
$modal-header-bg: #09090b;
$modal-header-border-color: rgba(255, 255, 255, 0.15);
$modal-header-color: #fafafa;

//== Dataview
$dataview-controls-bg: #09090b;
$dataview-controls-border-color: rgba(255, 255, 255, 0.15);
$dataview-emptymessage-bg: #000000;
$dataview-emptymessage-color: #71717a;

//== Alerts — Success
$alert-success-bg: #052e16;
$alert-success-color: #86efac;
$alert-success-border-color: #14532d;

//== Alerts — Warning
$alert-warning-bg: #422006;
$alert-warning-color: #fde68a;
$alert-warning-border-color: #713f12;

//== Alerts — Danger
$alert-danger-bg: #450a0a;
$alert-danger-color: #fca5a5;
$alert-danger-border-color: #7f1d1d;

//== Labels
$label-default-bg: #18181b;
$label-default-border-color: rgba(255, 255, 255, 0.15);
$label-default-color: #e4e4e7;
$label-primary-color: #09090b;
$label-success-color: #fafafa;
$label-warning-color: #09090b;
$label-danger-color: #fafafa;

//== Groupbox
$groupbox-default-bg: #09090b;
$groupbox-default-color: #e4e4e7;
$groupbox-primary-color: #09090b;
$groupbox-success-color: #fafafa;
$groupbox-warning-color: #09090b;
$groupbox-danger-color: #fafafa;
$groupbox-white-bg: #09090b;
$groupbox-white-color: #e4e4e7;

//== Callout
$callout-default-color: #e4e4e7;
$callout-default-bg: #09090b;
$callout-success-bg: #052e16;
$callout-warning-bg: #422006;
$callout-danger-bg: #450a0a;

//== Accordion
$accordion-header-default-bg: #09090b;
$accordion-header-default-bg-hover: #0f0f11;
$accordion-header-default-color: #fafafa;
$accordion-default-border-color: rgba(255, 255, 255, 0.15);
$accordion-bg-striped: #050507;
$accordion-bg-striped-hover: #0f0f11;

//== Wizard
$wizard-default-bg: #09090b;
$wizard-default-color: #e4e4e7;
$wizard-default-step-color: #71717a;
$wizard-default-border-color: rgba(255, 255, 255, 0.15);

//== Timeline
$timeline-border-color: rgba(255, 255, 255, 0.15);
$timeline-grouping-border-color: rgba(255, 255, 255, 0.15);
```

##:root block (required)

Because $use-css-variables: true, Atlas resolves colours from CSS custom properties at runtime. The SCSS variables above are not enough on their own — you must also add this :root { } block to custom-variables.scss. Without it, Atlas's default grey :root values override everything.

```css
:root {
  /* Brand Colors */
  --brand-primary: #fafafa;
  --brand-success: #22c55e;
  --brand-warning: #eab308;
  --brand-danger: #dc2626;
  --brand-default: #1c1c20;
  --gray: #71717a;

  /* Backgrounds */
  --bg-color: #000000;
  --bg-color-secondary: #09090b;

  /* Typography */
  --font-color-default: #e4e4e7;
  --font-color-detail: #a1a1aa;
  --font-color-header: #fafafa;
  --font-color-contrast: #09090b;

  /* Borders — white 15% opacity (shadcn/ui dark input border) */
  --border-color-default: rgba(255, 255, 255, 0.15);

  /* Links */
  --link-color: #60a5fa;
  --link-hover-color: #93c5fd;

  /* Topbar */
  --topbar-bg: #000000;
  --topbar-border-color: rgba(255, 255, 255, 0.15);
  --navbar-brand-name: #fafafa;

  /* Mobile Header */
  --m-header-bg: #000000;
  --m-header-color: #fafafa;

  /* Sidebar */
  --sidebar-bg: #000000;

  /* Navigation */
  --navigation-color: #e4e4e7;
  --navigation-color-hover: #fafafa;
  --navigation-color-active: #fafafa;
  --navigation-sub-color: #a1a1aa;
  --navigation-sub-color-hover: #fafafa;
  --navigation-sub-color-active: #fafafa;
  --navigation-bg: #000000;
  --navigation-bg-hover: #09090b;
  --navigation-bg-active: #09090b;
  --navigation-sub-bg: #09090b;
  --navigation-sub-bg-hover: #18181b;
  --navigation-sub-bg-active: #18181b;
  --navigation-border-color: rgba(255, 255, 255, 0.15);

  /* Sidebar Navigation */
  --navsidebar-bg: #000000;
  --navsidebar-bg-hover: #09090b;
  --navsidebar-bg-active: #09090b;
  --navsidebar-color: #e4e4e7;
  --navsidebar-color-hover: #fafafa;
  --navsidebar-color-active: #fafafa;
  --navsidebar-sub-bg: #09090b;
  --navsidebar-sub-bg-hover: #18181b;
  --navsidebar-sub-bg-active: #18181b;
  --navsidebar-sub-color: #a1a1aa;
  --navsidebar-sub-color-hover: #fafafa;
  --navsidebar-sub-color-active: #fafafa;
  --navsidebar-border-color: rgba(255, 255, 255, 0.15);

  /* Topbar Navigation */
  --navtopbar-bg: #000000;
  --navtopbar-bg-hover: #09090b;
  --navtopbar-bg-active: #09090b;
  --navtopbar-color: #e4e4e7;
  --navtopbar-color-hover: #fafafa;
  --navtopbar-color-active: #fafafa;
  --navtopbar-sub-bg: #09090b;
  --navtopbar-sub-bg-hover: #18181b;
  --navtopbar-sub-bg-active: #18181b;
  --navtopbar-sub-color: #a1a1aa;
  --navtopbar-sub-color-hover: #fafafa;
  --navtopbar-sub-color-active: #fafafa;
  --navtopbar-border-color: rgba(255, 255, 255, 0.15);

  /* Shadows */
  --shadow-color-border: rgba(0, 0, 0, 0.5);
  --shadow-color: rgba(0, 0, 0, 0.6);

  /* Form Inputs */
  --form-label-color: #e4e4e7;
  --form-input-bg: #09090b;
  --form-input-bg-focus: #09090b;
  --form-input-bg-hover: #0f0f11;
  --form-input-bg-disabled: #18181b;
  --form-input-color: #e4e4e7;
  --form-input-focus-color: #fafafa;
  --form-input-disabled-color: #52525b;
  --form-input-placeholder-color: #52525b;
  --form-input-border-color: rgba(255, 255, 255, 0.15);
  --form-input-border-focus-color: rgba(255, 255, 255, 0.35);
  --form-input-border-hover-color: rgba(255, 255, 255, 0.25);
  --form-input-static-border-color: rgba(255, 255, 255, 0.15);

  /* Buttons */
  --btn-default-bg: #09090b;
  --btn-default-border-color: rgba(255, 255, 255, 0.15);
  --btn-default-color: #e4e4e7;
  --btn-default-bg-hover: #18181b;
  --btn-default-icon-color: #a1a1aa;
  --btn-primary-bg: #fafafa;
  --btn-primary-border-color: #fafafa;
  --btn-primary-color: #09090b;
  --btn-primary-bg-hover: #e4e4e7;
  --btn-success-bg: #22c55e;
  --btn-success-border-color: #22c55e;
  --btn-success-color: #fafafa;
  --btn-success-bg-hover: #16a34a;
  --btn-warning-bg: #eab308;
  --btn-warning-border-color: #eab308;
  --btn-warning-color: #09090b;
  --btn-warning-bg-hover: #ca8a04;
  --btn-danger-bg: #dc2626;
  --btn-danger-border-color: #dc2626;
  --btn-danger-color: #fafafa;
  --btn-danger-bg-hover: #b91c1c;
  --btn-link-bg-hover: #09090b;

  /* Header */
  --header-bg-color: #000000;
  --header-text-color: #fafafa;
  --header-text-color-detail: rgba(255, 255, 255, 0.3);

  /* Grid */
  --grid-border-color: rgba(255, 255, 255, 0.15);
  --grid-bg: transparent;
  --grid-bg-header: #09090b;
  --grid-bg-hover: #0f0f11;
  --grid-bg-selected: #18181b;
  --grid-bg-selected-hover: #27272a;
  --grid-bg-striped: #050507;
  --grid-footer-bg: #09090b;
  --grid-selected-color: #fafafa;
  --grid-paging-color: #52525b;
  --grid-paging-color-hover: #fafafa;

  /* Tabs */
  --tabs-color: #a1a1aa;
  --tabs-color-active: #fafafa;
  --tabs-lined-color-active: #fafafa;
  --tabs-border-color: rgba(255, 255, 255, 0.15);
  --tabs-lined-border-color: #fafafa;
  --tabs-bg: transparent;
  --tabs-bg-pills: #18181b;
  --tabs-bg-hover: #09090b;
  --tabs-bg-active: #fafafa;

  /* Modal */
  --modal-header-bg: #09090b;
  --modal-header-border-color: rgba(255, 255, 255, 0.15);
  --modal-header-color: #fafafa;
  --modal-body-bg: #09090b;
  --modal-footer-bg: #09090b;

  /* Data View */
  --dataview-controls-bg: #09090b;
  --dataview-controls-border-color: rgba(255, 255, 255, 0.15);
  --dataview-emptymessage-bg: #000000;
  --dataview-emptymessage-color: #71717a;

  /* Cards */
  --card-bg: #09090b;
  --card-border: 1px solid rgba(255, 255, 255, 0.15);
  --card-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.5);

  /* Alerts */
  --alert-success-bg: #052e16;
  --alert-success-color: #86efac;
  --alert-success-border-color: #14532d;
  --alert-warning-bg: #422006;
  --alert-warning-color: #fde68a;
  --alert-warning-border-color: #713f12;
  --alert-danger-bg: #450a0a;
  --alert-danger-color: #fca5a5;
  --alert-danger-border-color: #7f1d1d;

  /* Labels */
  --label-default-bg: #18181b;
  --label-default-border-color: rgba(255, 255, 255, 0.15);
  --label-default-color: #e4e4e7;
  --label-primary-bg: #fafafa;
  --label-primary-border-color: #fafafa;
  --label-primary-color: #09090b;
  --label-success-bg: #22c55e;
  --label-success-border-color: #22c55e;
  --label-success-color: #fafafa;
  --label-warning-bg: #eab308;
  --label-warning-border-color: #eab308;
  --label-warning-color: #09090b;
  --label-danger-bg: #dc2626;
  --label-danger-border-color: #dc2626;
  --label-danger-color: #fafafa;

  /* Groupbox */
  --groupbox-default-bg: #09090b;
  --groupbox-default-color: #e4e4e7;
  --groupbox-white-bg: #09090b;
  --groupbox-white-color: #e4e4e7;

  /* Accordion */
  --accordion-header-default-bg: #09090b;
  --accordion-header-default-bg-hover: #0f0f11;
  --accordion-header-default-color: #fafafa;
  --accordion-default-border-color: rgba(255, 255, 255, 0.15);
  --accordion-bg-striped: #050507;
  --accordion-bg-striped-hover: #0f0f11;

  /* Wizard */
  --wizard-default-bg: #09090b;
  --wizard-default-color: #e4e4e7;
  --wizard-default-step-color: #71717a;
  --wizard-default-border-color: rgba(255, 255, 255, 0.15);

  /* Timeline */
  --timeline-border-color: rgba(255, 255, 255, 0.15);
  --timeline-grouping-border-color: rgba(255, 255, 255, 0.15);
}
```