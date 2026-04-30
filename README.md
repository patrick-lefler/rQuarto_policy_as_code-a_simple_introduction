# Policy as Code: A Simple Introduction

**Author:** Patrick Lefler  
**Published:** April 30, 2026  
**Rendered Output:** [View on GitHub Pages](https://patrick-lefler.github.io/rQuarto_policy_as_code-a_simple_introduction_2026-04-30/)

Expressing organizational compliance rules as executable, version-controlled logic rather than prose documents.

## Introduction

Most compliance programs run on PDFs. This project replaces that model with a working demonstration of Policy as Code — rules expressed as functions that take inputs, evaluate conditions, and return deterministic verdicts. The entry point is deliberately simple: password complexity validation. The argument is not.

## Overview

The document introduces Policy as Code through a six-condition password validation function implemented in C# using regular expressions. Each condition — minimum length, maximum length, uppercase, lowercase, numeric digit, special character — is encoded as a discrete, testable step. The workflow is visualized as a Mermaid flowchart rendered natively in Quarto. The closing sections make the case for why this pattern matters to GRC teams, boards, and engineers: it converts compliance from periodic attestation into continuous, auditable enforcement. The target audience is anyone responsible for the gap between what an organization promises regulators and what it actually does.

## Tech Stack

- **Language:** R
- **Framework:** [Quarto](https://quarto.org/)
- **Primary Libraries:** tidyverse, knitr, kableExtra, plotly, scales, sessioninfo
- **Diagram Tooling:** Mermaid (via Quarto-native rendering)
- **Deployment / Output:** Self-contained HTML document

## Repository Structure

```
├── data/               # Raw and processed data
├── scripts/            # Helper R scripts
├── models/             # Saved model objects (.rds)
├── output/             # Rendered HTML files
├── _brand.yml          # Brand color and typography configuration
├── _quarto.yml         # Project configuration
└── index.qmd           # Main Quarto entry point
```

## Key Findings

1. **The failure message is the product.** A prose policy that says "passwords must be complex" generates interpretation. A coded policy that returns `FAIL: no special character` eliminates it. That shift — from vague guidance to specific, actionable output — is what compliance teams actually deliver when they adopt this pattern.

2. **Version control is the strongest argument for the approach.** When a policy lives in a Git repository, every change carries a timestamp, an author, and a diff. An auditor can reconstruct the full history of a rule in minutes, not weeks.

3. **The organizational cost is real and worth naming.** Writing policy as executable logic requires compliance professionals to read code and engineers to treat governance as a first-class design input. Neither adjustment is free. Companies that defer this investment will continue to discover compliance gaps during incidents, when remediation is most expensive.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contact

Patrick Lefler — [LinkedIn](https://www.linkedin.com/in/patricklefler/) | [Website](https://patrick-lefler.github.io) | [Substack](https://substack.com/@pflefler)
