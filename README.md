# PQID Dataset Gateway

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20024477.svg)](https://doi.org/10.5281/zenodo.20024477)
[![Open in Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/open-in-hf-spaces-sm.svg)](https://huggingface.co/spaces/Elias-Abebe-Gasparini/PQID-Dataset-Gateway)

Interactive research software for auditing and exploring the Parallel Quantum
Instruction Dataset (PQID).

The gateway brings the public dataset release, construction pipeline,
license-governance logic, manuscript figures, release-integrity checks, and
reviewer-facing links into one navigable interface. It is a companion software
artifact for the PQID dataset release rather than the canonical dataset itself.

## Live Artifacts

- Hugging Face Space: <https://huggingface.co/spaces/Elias-Abebe-Gasparini/PQID-Dataset-Gateway>
- Hugging Face dataset: <https://huggingface.co/datasets/Elias-Abebe-Gasparini/PQID>
- GitHub dataset snapshot: <https://github.com/Elias-Abebe-Gasparini/PQID-Dataset/tree/v1.0.0-scientific-data-submission>
- Zenodo DOI: <https://doi.org/10.5281/zenodo.20024477>

## What The Gateway Does

- Interactive D3 construction-pipeline explorer
- Release-flow and public-open dataset stratification view
- Exact-license and license-behaviour explorer
- Quality and remediation audit panel
- Public-open dataset row preview
- Attribution manifest search
- Manuscript figure browser with large preview
- Release-integrity panel with static and live Hugging Face checks
- Reviewer Mode linking the public data, GitHub snapshot, Zenodo DOI, and issue tracker

## Repository Layout

```text
.
|-- README.md                         # GitHub-facing portfolio/research-software overview
|-- docs/
|   |-- PORTFOLIO_CASE_STUDY.md       # Short project narrative and engineering contribution
|   `-- REUSE_TEMPLATE.md             # How to adapt this gateway pattern to future datasets
`-- space/
    |-- app.py                        # Gradio application
    |-- README.md                     # Hugging Face Space metadata and Space README
    |-- requirements.txt              # Space runtime dependencies
    |-- assets/figures/               # Packaged public figure assets
    |-- check_gradio_space.py         # Structural audit script
    |-- gradio_space_audit.ipynb      # Documented audit/deploy notebook template
    |-- upload_space.py               # Hugging Face Space upload helper
    |-- run_local_space.ps1           # Optional Windows local preview helper
    `-- SPACE_UPLOAD_CHECKLIST.md     # Manual upload and smoke-test checklist
```

## Technical Stack

- Gradio for the dashboard interface
- Hugging Face Spaces for public hosting
- Hugging Face Datasets for public-open dataset access
- D3.js for interactive pipeline and governance visualizations
- pandas for tabular release summaries and integrity checks
- Zenodo for immutable archival citation
- GitHub for reproducibility scripts and versioned release metadata

## Auditability

The workflow is documented in:

```text
space/gradio_space_audit.ipynb
```

The notebook checks:

- runtime files and figure assets
- Hugging Face Space metadata
- public artifact links
- configured private-marker hygiene
- structural Space package validity
- dashboard importability
- static release-integrity checks
- optional live Hugging Face summary validation
- optional local preview and guarded Space upload

The command-line checker provides a faster audit path:

```powershell
python "space\check_gradio_space.py" --skip-import
```

## Deployment

The Space can be updated with:

```powershell
python "space\upload_space.py" --repo-id "Elias-Abebe-Gasparini/PQID-Dataset-Gateway"
```

The upload helper publishes only runtime files and packaged public figure assets
by default. Audit/helper files stay local unless `--include-audit-files` is
explicitly passed.

## Relationship To PQID

The canonical dataset and reproducibility anchor remain in `PQID-Dataset`. This
repository is the companion interface layer: it demonstrates how the release can
be inspected, checked, and explained without redistributing restricted
no-license rows.

## License Note

Dataset use is governed by the PQID dataset card and archival release materials.
Add a separate software license file if you want to license the dashboard code
independently from the dataset and figure assets.
