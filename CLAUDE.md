# Rasa Docs — Authoring Conventions

This file captures the style and structure conventions for the Rasa partner documentation site. All authors and coding agents must follow these rules so the docs stay consistent.

---

## Site Structure

The docs have **two products**, configured as tabs in `docs.json`:

| Tab | Path prefix | Audience |
|-----|-------------|----------|
| Studio | `studio/` | Business users, conversation designers |
| Rasa Pro | `pro/` | Developers, engineers |

**Maestro** is a section _inside_ Rasa Pro (`pro/maestro/`), never a separate top-level product. It must never have its own version dropdown.

Within each product, navigation follows **Diátaxis** in this order:
1. **Get Started** — tutorials and quickstarts
2. **Guides** — task-oriented how-tos
3. **Concepts** — explanatory content
4. **Reference** — changelogs, API reference, config reference

---

## Authentication

The entire site is partner-gated using Mintlify Auth (`"type": "password"` in `docs.json`). Do **not** add `"public": true` to any page.

To move a section to partial auth later, add `groups: ["partners"]` to the frontmatter — do not mark pages public yet.

---

## Frontmatter Requirements

Every `.mdx` file **must** include:

```yaml
---
title: "Page Title — 50–60 characters, unique, SEO-friendly"
sidebarTitle: "Short Label"
description: "130–155 characters. Describes the page content — not a restatement of the title."
---
```

- **`title`**: 50–60 chars. Verb-led for guides ("Configure your agent"), noun-led for concepts ("What is CALM?"). Must be unique across the site.
- **`sidebarTitle`**: 1–3 words, Title Case. Never repeats the product name. Examples: "Introduction", "Quickstart", "Custom Actions", "What is Maestro".
- **`description`**: 130–155 chars. Used in llms.txt and search previews. Must add information beyond the title.

---

## Opening Paragraph

Every page **must** open with a plain-prose paragraph immediately after the frontmatter — before any component, callout, or code block. It must:

- Name the feature/product
- State what this page covers or what the reader will accomplish
- Add information beyond the title and description

❌ Bad: `This page covers authentication.`
✅ Good: `Rasa Studio authenticates Studio API requests using Keycloak's Client Credentials flow. This page walks you through creating a Keycloak client, obtaining a client secret, and using it to get a Bearer token for API calls.`

---

## Page Conventions

### Components to use

| Use case | Component |
|----------|-----------|
| Sequential instructions | `<Steps>` / `<Step>` |
| Multiple language/tool variants | `<CodeGroup>` |
| Alternative views | `<Tabs>` / `<Tab>` |
| Feature or link grids | `<CardGroup cols={2}>` / `<Card>` |
| Important notes | `<Note>` |
| Breaking changes | `<Warning>` |
| Tips | `<Tip>` |
| Collapsible FAQs | `<Accordion>` |

**Never** use raw HTML `<div>`, `<a>`, or Tailwind classes for cards or layouts. Always use `<Card>` and `<CardGroup>`.

### Code blocks

- Always include a language tag (` ```python `, ` ```yaml `, ` ```bash `)
- Use a filename title where helpful (` ```yaml config.yml `)
- Use `<CodeGroup>` for multi-language/multi-file examples
- Never manually style code blocks — Mintlify handles theming automatically

### Callouts

Use sparingly — one or two per page maximum. Don't use `<Note>` for content that belongs in the main body.

---

## Content Tone

- **Second person** ("you", "your agent") — address the reader directly
- **Active voice** and **imperative mood** for instructions ("Run `rasa train`", not "The model can be trained by running…")
- **Lead with the user's goal**, not the implementation details
- **Studio pages** are screenshot-driven (describe UI steps clearly)
- **Pro/Maestro pages** are code-first (lead with working code examples)

---

## Quickstart Rule

Quickstart pages must get the reader to a **working result in under 10 minutes of reading**. No long preamble — get to the first command within the first `<Steps>` block.

---

## Changelogs

Both products have a changelog page using the `<Update>` component:
- `studio/reference/changelog.mdx`
- `pro/reference/changelog.mdx`

New release notes go at the **top** of the file. Each entry uses:
```mdx
<Update label="v2.0.0" description="Released 2026-01-01">
  Changes here...
</Update>
```

---

## File Naming

- Lowercase, hyphen-separated: `what-is-studio.mdx`, `custom-actions.mdx`
- Match the path slug in `docs.json` exactly
- No `index.mdx` files inside product subdirectories — use the named file (e.g., `studio/what-is-studio.mdx`)

---

## docs.json Rules

- `navigation` must be an **object** with `tabs` — never an array
- Max 2 levels of groups per tab
- No empty groups — every group must have at least 2 pages
- Primary color: `#5A17EE` (use sparingly for links, active nav, primary buttons only)
- Auth: `"type": "password"` — do not remove until public launch

---

## Out of Scope (Phase 1)

The following are explicitly not part of this phase:
- Version dropdowns (Pro versioning comes later)
- OpenAPI / REST API reference
- Migration of existing Docusaurus content
- Custom CSS or components beyond Mintlify built-ins
