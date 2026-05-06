# Reusing The Dataset Gateway Pattern

This repository can be used as a template for future dataset-gateway projects.

## 1. Replace Project Configuration

Update the configuration values in:

```text
space/app.py
space/gradio_space_audit.ipynb
space/README.md
```

Replace:

- dataset repository ID
- Space repository ID
- GitHub snapshot URL
- Zenodo DOI
- expected release counts
- expected figure filenames
- attribution and summary file paths

## 2. Replace Public Assets

Put public figures or screenshots in:

```text
space/assets/figures/
```

Do not include private drafts, funding notes, internal review sheets, or
restricted/no-license data.

## 3. Keep Deployment Minimal

The default upload should include only:

```text
app.py
README.md
requirements.txt
assets/figures/*.png
```

Audit notebooks and helper scripts can remain in GitHub, but they do not need to
be uploaded to the Hugging Face Space runtime unless intentionally public.

## 4. Run The Audit

Before upload:

```powershell
python "space\check_gradio_space.py" --skip-import
```

Then run:

```text
space/gradio_space_audit.ipynb
```

Use the live Hugging Face check only when network access is available and the
dataset repository has already been published.

## 5. Upload

```powershell
python "space\upload_space.py" --repo-id "YOUR_USERNAME/YOUR_SPACE_NAME"
```

## 6. Smoke Test

After the Space rebuilds, verify:

- public links open correctly
- D3 panels render and respond
- dataset row preview loads
- attribution search works
- figure selector changes the large preview
- release-integrity static checks are all `OK`
- live summary check matches the expected public total

## 7. Portfolio Framing

Frame the project as:

```text
interactive dataset infrastructure
release-governance dashboard
research-software companion artifact
auditable data-publication gateway
```

That description is more accurate and stronger than calling it only a demo.
