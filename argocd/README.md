# Argo CD — Ignore-Differences Editor (argoproj/argo-cd#29330)

Assets for the in-UI "ignore differences" editor proposal.

## Vector flow (SVG)

![Ignore-differences editor — core flow](./ignore-rule-flow-en.svg)

## Annotated flow with UI screenshots

[`ignore-rule-flow.html`](./ignore-rule-flow.html) — step-by-step flow with
prototype screenshots (diff entry → inline drawer with live impact preview →
save feedback → rule management).

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
