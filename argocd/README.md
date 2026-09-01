# Argo CD — Ignore-Differences Editor (argoproj/argo-cd#29330)

Assets for the in-UI "ignore differences" editor proposal. English only, SVG only.

## Full annotated flow (embedded UI screenshots)

![Annotated interaction flow](./ignore-rule-flow-annotated-en.svg)

## Compact flow (nodes only)

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
