# Portfolio Case Study: PQID Dataset Gateway

## Summary

The PQID Dataset Gateway is an interactive research-software layer for the
Parallel Quantum Instruction Dataset. It was built to make a complex dataset
release easier to inspect by reviewers, downstream users, and future maintainers.

The gateway connects the public Hugging Face dataset, GitHub release snapshot,
Zenodo DOI, manuscript figures, license-governance logic, quality-audit evidence,
and attribution workflows in one public Gradio interface.

## Problem

PQID is not a simple static dataset. Its construction involved GitHub API data
collection, schema normalization, OpenAI API instruction generation, semantic
quality validation, remediation of rewrite-risk rows, and license-aware release
stratification.

Reviewers and users need to understand not only what the public data contains,
but why some rows are public-open, why others are restricted, how quality checks
were layered, and where immutable release evidence can be inspected.

## Contribution

The gateway turns those release-governance and quality-control decisions into
auditable interface components:

- pipeline explorer for construction stages
- release-flow visualization for public-open and restricted rows
- license explorer for exact licenses and behaviour families
- quality audit panel for validation and remediation evidence
- figure browser for manuscript visuals
- release-integrity panel for static and live consistency checks
- reviewer mode for fast access to dataset, code, DOI, attribution, and issues

## Engineering Decisions

The implementation uses native Gradio components where reliable state updates
matter, and D3 iframe visualizations where richer interactive diagrams are useful.
This avoids fragile inline JavaScript inside Gradio HTML blocks for controls such
as figure selection.

The Space package also includes a documented audit notebook and command-line
checker so the deployment can be verified before every update.

## Challenges

- preserving dark-mode readability on Hugging Face Spaces
- packaging figure assets reliably for hosted previews
- avoiding leakage of private manuscript or funding files
- separating public-open release views from restricted no-license materials
- keeping deployment reproducible despite local Python dependency friction

## Outcome

The result is a reusable dataset-gateway pattern for research data releases that
need more than a static README: provenance navigation, release integrity,
governance explanation, and reviewer-facing audit paths.
