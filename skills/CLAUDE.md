# Maia Agent Skills

This directory contains Maia Agent Skills for Mendix Studio Pro. Skills live in `skillssource/` and follow the [Agent Skills Specification](https://agentskills.io/specification).

## Directory Structure

```
skillssource/
  dark-mode-styling/
    SKILL.md                          # Skill definition + all variable mappings
    references/
      variable-overrides.md           # Copy-paste SCSS + :root block
```

## dark-mode-styling

Comprehensive dark mode theme for Mendix Atlas UI 3, inspired by shadcn/ui's pure-black palette. Covers ~130 SCSS variables across all widget categories.

### Activation

Dark mode is controlled by a `$dark-mode: true/false` SCSS variable at the top of `custom-variables.scss`. All overrides and the `:root` block are wrapped in `@if $dark-mode { }`, so setting it to `false` cleanly disables dark mode without removing any code.

### Design Decisions

- Base canvas is true black `#000000`, elevated surfaces at `#09090b`
- Borders use `rgba(255, 255, 255, 0.15)` (white at 15% opacity) matching shadcn/ui's `--input` token
- Primary buttons are inverted: white bg `#fafafa` with black text `#09090b`
- Color palette derived from shadcn/ui zinc dark: `#000000` → `#09090b` → `#0f0f11` → `#18181b` → `#27272a`

### Critical: Dual Override Requirement

Atlas uses `$use-css-variables: true`, so SCSS `$variable` overrides alone are **not enough**. The theme must include both:

1. SCSS variable overrides (e.g. `$bg-color: #000000;`)
2. A `:root { }` block with matching CSS custom properties (e.g. `--bg-color: #000000;`)

Without the `:root` block, Atlas's default CSS custom property values win at runtime and the theme appears grey.

### Atlas Variable Reference

The full Atlas SCSS variable catalog lives at:
`/Users/joshua.moesa/workdir/github/mendix/atlas/packages/theming/atlas/src/themesource/atlas_core/web/_variables.scss`

App-level overrides go in `theme/web/custom-variables.scss` inside the Mendix project.

## Creating New Skills

1. Create `skillssource/<skill-name>/SKILL.md` with YAML frontmatter:
   ```yaml
   ---
   name: <skill-name>
   description: What the skill does and when Maia should use it.
   ---
   ```
2. `name` must match the parent directory name exactly
3. Keep `SKILL.md` under 500 lines; move detailed content to `references/`
4. Sync in Studio Pro: **F4** or the **Sync** button in the Skills pane
5. Module-level skills go under `skillssource/_modules/<module_name>/`
