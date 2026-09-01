# Argo CD — Ignore-Differences Editor (argoproj/argo-cd#29330)

Assets for the in-UI "ignore differences" editor proposal.
Screenshots live in [`assets/`](./assets) and are referenced from markdown —
reference them the same way in issue comments via their raw URLs.

## Core flow (SVG, vector)

![Core flow](./ignore-rule-flow-en.svg)

## Step-by-step with UI screenshots

### Steps 1–2 · Diff tab — inline "Ignore…" entry on the added row

![Diff tab with inline Ignore entry](./assets/flow-shot-diff.png)

### Steps 3–4 · Editor drawer — live impact preview, ‹ n/N › match navigation

Scope and pointer are prefilled from the clicked row; the impact bar and
"will ignore" row highlights update on every keystroke.

![Drawer with live impact preview](./assets/flow-shot-drawer.png)

### Step 5 · Save — rows turn grey "ignored", card badges, confirmation toast

![Saved state](./assets/flow-shot-saved.png)

### Step 6 · Manage in Ignored Fields — rule list, validation, Preview Against Manifests

![Ignored Fields management](./assets/flow-shot-manage.png)

## Mermaid (paste directly into GitHub comments)

```mermaid
flowchart TD
  A["1. Open the Diff tab"] --> B["2. Hover a diff row, click Ignore"]
  B --> C["3. Drawer slides in (same view)<br/>Scope + pointer prefilled"]
  C --> D{"Pointer valid?"}
  D -- "inline error, fix pointer" --> C
  D -- "valid" --> E["4. Live impact preview<br/>Eliminates N of M open diffs"]
  E --> F{"Matches expectation?"}
  F -- "No: adjust scope (empty Name = all)" --> C
  F -- "Yes" --> G["5. Save rule"]
  G --> H["Rows turn grey ignored, badge, toast"]
  H --> I["6. Manage in Ignored Fields<br/>Preview / Add to Rule"]
  H -. "View rule, edit again" .-> C
```

> Note: the SVG keeps no external image references on purpose — GitHub blocks
> external resources inside SVGs rendered as images, so screenshots are plain
> repo files referenced from markdown instead.
