# CLAUDE.md — mendix-howtos

## Project overview

Personal repo hosting the **Mendix AI Experience** workshop — a hands-on enablement workshop covering GenAI Commons, Conversational UI, Knowledge Base, RAG, Agent Builder, and MCP on the Mendix platform.

Hosted on **GitHub Pages** at the repo's GitLab/GitHub Pages URL. All user-facing content lives in `docs/`.

## Repository structure

```
docs/                       # GitLab/GitHub Pages root
  index.html                # Hub page — links to workshop versions
  ai-workshop-1112.html     # Workshop for Studio Pro 11.12
  ai-workshop-1114.html     # Workshop for Studio Pro 11.14
  ai-workshop-1115.html     # Workshop for Studio Pro 11.15 (latest)
  *.pdf                     # Workbook PDFs per version (v3.2, v4.0, v5.0)
  *.zip                     # Solution zips for workbook exercises
  robots.txt                # Disallow all crawlers
images/                     # Repo images (howto guides)
skills/                     # Claude Code skills
```

## Design system

All HTML pages follow the **Siemens proposal-template** design language:

- **Font**: Inter (Google Fonts), 16px base, line-height 1.55
- **Colors**: `--siemens-petrol: #009999`, `--ink: #1A1A1A`, `--ink-soft: #555`, `--rule: #E5E5E5`, `--bg: #FFFFFF`, `--bg-soft: #F7F7F7`
- **Header**: Petrol brand mark, `border-bottom: 2px solid petrol`
- **Hero**: Uppercase eyebrow (12px, 0.08em tracking), bold h1, subtitle
- **Cards**: 4px top accent bar, 1px border, 4px radius, subtle hover lift
- **Workshop cards**: Blue (#2d6bff), green (#27c7c3), red (#e20015) accent colors for workbooks 1/2/3
- **Hub cards**: All petrol accent
- **CTAs**: Underlined text links (petrol), not pill buttons
- **Notice box**: `border-left: 4px solid var(--rule)`, bg-soft background
- **Footer**: `border-top: 1px solid var(--rule)`, 11px, centered

## Analytics

Google Analytics 4 (`G-LRJTK25SHP`) with consent-gated loading. The consent banner and GA script are present on all pages. Custom events:

- `version_click` — hub page, tracks which workshop version is selected
- `workbook_click` — workshop pages, tracks PDF/zip downloads with `workshop_version`, `workbook_name`, `link_label`, `link_url`

## Conventions

- Pages are standalone single-file HTML (inline CSS, no external stylesheets)
- No build step — edit HTML directly
- Each workshop version has its own page with version-specific PDF links, solution zips, and GA `workshop_version` tag
- Workbook PDFs follow naming: `Mendix AI Experience 2026 MxXXXX - Workbook N vX.X.pdf`
- All pages include aggressive `noindex`/`nofollow` meta tags — content is for internal enablement only
- `robots.txt` disallows all user agents

## When adding a new workshop version

1. Copy the latest `ai-workshop-XXXX.html` as a template
2. Update: eyebrow version, date, PDF filenames, solution zip references, GA `workshop_version`
3. Add a new card to `index.html` — move the "Latest" badge to the new card
4. Upload new PDFs and solution zips to `docs/`
