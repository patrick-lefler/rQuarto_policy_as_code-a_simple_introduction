# Policy as Code: A Simple Introduction

**Author:** Patrick Lefler  
**Published:** April 30, 2026  
**Rendered Output:** [View on GitHub Pages](#)

---

## Overview

Policy as Code is the practice of expressing organizational rules as executable, version-controlled logic rather than prose documents. This project introduces the concept through the simplest possible worked example — a six-condition password complexity validator — to make the pattern legible to both compliance professionals and engineers. The argument is organizational as much as technical: a rule that lives in a Git repository can be tested, audited, and automatically enforced; a rule that lives in a PDF cannot.

---

## Methodology

The document builds the concept in four layers. First, it establishes the failure mode of prose-based policy: ambiguity of interpretation, manual enforcement, and the gap between what the organization promises regulators and what it actually does. Second, it specifies the password policy as six independent, sequentially evaluated conditions — minimum and maximum length, uppercase, lowercase, numeric, and special-character requirements — each returning a named failure state on rejection. Third, it renders the evaluation logic as a Mermaid flowchart, tracing every decision branch from input string to `PASS` or a specific `FAIL` message. Fourth, it constructs the equivalent C# regex implementation in six steps, from individual conditions to a single composite expression, demonstrating that the flowchart and the code are the same artifact in two notations.

---

## Key Findings

- A coded policy that returns `FAIL: no special character` eliminates the interpretive ambiguity that a prose policy generates. The failure message — not the pass — is the primary product of expressing policy as executable logic.
- The six-condition password validator produces six distinct, actionable rejection states. Each maps to a one-line change in source code if the organization modifies the requirement, with a clear diff in version history.
- When policy lives in a Git repository, an auditor can reconstruct the complete history of a rule — author, timestamp, and diff — in minutes. The same reconstruction from a document management system typically takes weeks.
- The organizational cost is real and worth naming: compliance professionals must be able to read pull requests with enough fluency to confirm the logic matches the intent; engineers must treat governance constraints as first-class design inputs rather than pre-audit checkboxes.

---

## Project Structure

```
├── index.qmd          # Source document
├── _brand.yml         # Brand color and typography configuration
├── docs/
│   └── index.html     # Rendered output (GitHub Pages root)
└── README.md
```
---

## Requirements

- R ≥ 4.5.2
- Quarto ≥ 1.8.26

```r
install.packages(c("tidyverse", "scales", "knitr", "kableExtra", "plotly", "sessioninfo"))
```

The rendered HTML is written to `docs/index.html` for GitHub Pages hosting.

---

## License

© 2026 Patrick Lefler. All rights reserved.
