# Argo CD — Ignore-Differences Editor (argoproj/argo-cd#29330)

English-only assets for the in-UI "ignore differences" editor proposal.
The two annotated SVGs below are fully self-contained (screenshots embedded)
— reference either directly in issue comments via its raw URL.

## Part 1/2 — Discover & Draft (steps 1–4, validation & scope loops)

![Part 1 — Discover & Draft](./ignore-rule-flow-part1-en.svg)

## Part 2/2 — Save & Manage (steps 5–6, "View rule" re-entry)

![Part 2 — Save & Manage](./ignore-rule-flow-part2-en.svg)

## Compact flow (nodes only, 5 KB)

![Core flow](./ignore-rule-flow-en.svg)

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

Raw screenshots (PNG sources) live in [`assets/`](./assets).
