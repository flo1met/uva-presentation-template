# UvA RevealJS — Quarto Presentation Template

A Quarto extension for creating academic presentations with University of Amsterdam branding.

---

## Installation

Run the following command inside your project folder:

```bash
quarto add flo1met/uva-presentation-template
```

This will install the extension into `_extensions/uva/` within your project.

---

## Creating a new presentation

To start from the template (copies `template.qmd` into your project):

```bash
quarto use template flo1met/uva-presentation-template
```

Or, after installing the extension manually, create a `.qmd` file with this YAML header:

```yaml
---
title: "Your Presentation Title"
subtitle: "Conference Name / Subtitle"
author: "Your Name"
institute: "University of Amsterdam"
date: today
date-format: "MMMM YYYY"

format:
  uva-revealjs:
    footer: "Short title — Your Name | University of Amsterdam"
---
```

---

## Rendering

```bash
quarto render your-presentation.qmd
```

Or use the **Render** button in RStudio / VS Code. The output is a self-contained HTML file (`embed-resources: true`), ready to present from any machine without an internet connection.

---

## Slide types and helper classes

### Section divider (full red background)

```markdown
# Section Title {.section-slide}
```

### Two-column layout

```markdown
:::: {.columns}
::: {.column width="50%"}
Left content
:::
::: {.column width="50%"}
Right content
:::
::::
```

### Text size helpers

| Class | Size |
|---|---|
| `.small-text` | 75% |
| `.tiny-text` | 62% |
| `.center-text` | centred |
| `.highlight-red` | UvA red, bold |

Apply inline with a Quarto span: `[some text]{.highlight-red}`

### Callout boxes

```markdown
::: {.callout-note}
A note styled with UvA red.
:::

::: {.callout-tip}
A tip styled in green.
:::
```

### Incremental reveal

```markdown
Content shown immediately.

. . .

Content revealed on next click.
```

---

## Overriding defaults

Any format option from the extension can be overridden per-presentation in the YAML:

```yaml
format:
  uva-revealjs:
    footer: "Custom footer text"
    slide-number: false
    embed-resources: false   # faster render during drafting
```

---

## File structure

```
_extensions/
└── uva/
    ├── _extension.yml          # extension metadata and format defaults
    ├── uva-theme.scss          # SCSS theme (UvA brand colours and styles)
    ├── _partials/
    │   └── title-slide.html    # custom title slide layout
    ├── logo-regular_uva.webp   # UvA wordmark (footer logo)
    └── logo_uva.webp           # UvA shield (alternative)
template.qmd                    # starter template copied on `quarto use template`
```

---

## Updating the extension

```bash
quarto update flo1met/uva-presentation-template
```

---


