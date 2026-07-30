# JAD Submission Package — MDD ↔ Anxiety Bidirectional MR

Manuscript + figures + supplementary materials for the Journal of Affective Disorders (JAD) submission titled (working title):

> **Bidirectional Mendelian randomization analysis of major depressive disorder and anxiety disorders reveals shared genetic architecture**

---

## Figure Re-Render Version — **v3.1 (2026-07-30)**

This package contains the **second re-render pass** of all figures to meet high-impact SCI submission standards (vector graphics, journal-acceptable page sizes, font consistency, no arrow/element distortion).

### What changed vs. v3.0 (first re-render)

| Issue | v3.0 | v3.1 (this version) |
|---|---|---|
| Arrow / connector markers | Rasterised via Pillow → blurred, **visibly deformed** | Native SVG `<marker>` (`markerUnits="userSpaceOnUse"`) → crisp at any DPI |
| Figure 1 rasteriser | Pillow (no SVG marker support) | resvg-js (node) → true vector → clean arrowheads |
| Vector PDF for submission systems | not provided | All 8 figures exported as vector PDF (A4-family page sizes) via PyMuPDF |
| Figure 1 — MVMR covariate box | Stated **6 covariates** (BMI / education / smoking / alcohol / physical activity / insomnia) — **inconsistent with manuscript §2.5** which adjusts for **3 covariates** | Corrected to **3 covariates: BMI, education, smoking initiation** (limitations section explicitly notes alcohol use / sleep traits were *not* modelled) |
| Figure 1 — cell-type annotation | Stated **LDSC-SEG: GABAergic interneurons, microglia, pyramidal neurons** — *no occurrence of these terms in the manuscript text* | Replaced with text-supported: **Gene-set enrichment (synaptic, GABAergic, neurodevelopmental pathways)** + **Drug-target candidates from colocalization loci (MCHR1, SORCS3, VRK2, FURIN)** |

All other figures (Figure 2 / 3 / S1 / S2 / S3 / S4) were verified against the manuscript text and required **no further content correction** — only the rasteriser swap (resvg) and vector-PDF export.

---

## Figure inventory

All figures ship in three formats:

| File | Format | Use |
|---|---|---|
| `<name>.svg` | Vector source | Authoritative source of truth; edit here and re-export |
| `<name>.png` | High-res raster (≈ 3000 px wide, ~425 DPI @ 180 mm double column) | Inline in manuscript docx, preview |
| `vectorPDF_<name>.pdf` | True vector PDF, A4-family page size | Submission system upload (vector format) |

| # | File (prefix) | Caption (short) |
|---|---|---|
| Fig 1 | `Figure_1_Study_Design_Workflow` | Study design and workflow of the bidirectional MR, instrument-strength and Steiger directionality assessment, MVMR, LDSC, colocalization, and functional annotation analyses |
| Fig 2 | `Figure_2_Bidirectional_MR_Forest_Plot` | Forest plot of bidirectional MR estimates between MDD and anxiety |
| Fig 3 | `Figure_3_MVMR_Forest_Plot` | MVMR forest plot (adjusted for BMI, education, smoking initiation) |
| S1 | `Supplementary_Figure_S1_MR_Scatter_Plots` | MR scatter plots |
| S2 | `Supplementary_Figure_S2_Leave_One_Out` | Leave-one-out sensitivity |
| S3 | `Supplementary_Figure_S3_Funnel_Plots` | Funnel plots (asymmetry assessment) |
| S4 | `Supplementary_Figure_S4_GSEA_Bubble_Plot` | GSEA / pathway enrichment bubble plot |
| S5 | `Supplementary_Figure_S5_Shared_Genetic_Architecture` | Shared genetic architecture: colocalization + LDSC rg + functional annotation |

---

## Rendering pipeline (for reproducibility)

```text
SVG source  ──► resvg-js (node)  ──►  PNG (3000 px, 425 DPI)   ← inline in docx
            └─► PyMuPDF (fitz)  ──►  Vector PDF (A4 family)    ← submission upload
```

* **resvg-js** v0.x — vector → raster (used for inline docx preview / older systems that want TIFF/PNG)
* **PyMuPDF** 1.28.0 (`fitz`) — SVG → true-vector PDF; markers (arrowheads) preserved as vector; text embedded with MuPDF font engine
* **Font**: Arial / Arial-Bold (system, embedded into PDF)
* No native cairo / inkscape / ghostscript required.

### Re-render from source

```bash
# PNG (from managed node workspace, where resvg-js is installed)
node render_all_figs.cjs

# Vector PDF
python svg_to_pdf_fitz.py        # raw conversion (native page size)
python normalize_pdf_size.py     # reshape to A4 family (vector kept)
```

---

## Manuscript ↔ figure consistency (verified 2026-07-30)

Cross-checked every numeric / categorical claim in the figures (see inventory above, all at repository root) against `Manuscript_Main_Text_JAD_Revised_v3.docx`:

* MDD GWAS: **412,305 cases / 1,588,397 controls** (PGC 2025, European-ancestry subset)
* Anxiety GWAS: **122,083 cases / 729,602 controls** (PGC 2026, European-ancestry subset)
* SNPs (clumped): **198 (MDD instruments), 50 (anxiety instruments)**
* F-statistics: **mean F = 44.0 (MDD→anxiety), 37.9 (anxiety→MDD)**
* Steiger directionality: **P = 0.018 (MDD→anxiety), P = 1.9 × 10⁻⁹⁵ (anxiety→MDD)**
* MRlap cross-trait λ = **0.256 (SE 0.009)**
* Genetic correlation (LDSC): **rg = 0.90, SE = 0.032, P < 1 × 10⁻¹⁰⁰**
* Colocalization: **11 loci with PP.H4 > 0.95** (of 375 tested)
* MVMR (BMI / education / smoking initiation): **OR = 1.15 (95% CI 1.09–1.22)**

---

## Submission package layout

```
Causal-Inference-1/   ← GitHub repo, FLAT: every file sits at the repository root (no sub-folders)

  README.md                                          ← this file
  .gitignore
  Manuscript_Main_Text_JAD_Revised_v3.docx          ← CURRENT main text (Figure 1 embedded)
  Manuscript_Main_Text_JAD.docx / _with_Authors_Funding.docx / _with_Figure_Calls.docx / _Revised.docx
  Cover_Letter.docx / Cover_Letter_JAD.docx
  Title_Page_JAD.docx / Abstract.docx / Highlights_JAD.docx / Figure_Captions_JAD.docx
  Ethics_Statement.docx / Data_Availability_Statement.docx / Declaration_of_Competing_Interest.docx / Funding_Statement.docx
  JAD_Submission_Checklist.docx / STROBE-MR_Checklist.md
  Supplementary_Table_S9_STROBE-MR_Checklist.docx / Supplementary_Tables_S1-S8_JAD.docx
  Revision_Notes.md / Package_File_List.txt / README_Submission_Package.txt
  supplementary_analysis.R
  S1_MDD_to_Anxiety_harmonised_198_instruments.csv / S2_Anxiety_to_MDD_harmonised_50_instruments.csv
  S8_with_genes_final.xlsx

  Figures (8 × {svg, png, pdf} = 24 files, all at root):
    Figure_1_Study_Design_Workflow.{svg,png,pdf}            # Fig 1, re-rendered (crisp arrows, 3 MVMR covariates)
    Figure_2_Bidirectional_MR_Forest_Plot.{svg,png,pdf}
    Figure_3_MVMR_Forest_Plot.{svg,png,pdf}
    Supplementary_Figure_S1_MR_Scatter_Plots.{svg,png,pdf}
    Supplementary_Figure_S2_Leave_One_Out.{svg,png,pdf}
    Supplementary_Figure_S3_Funnel_Plots.{svg,png,pdf}
    Supplementary_Figure_S4_GSEA_Bubble_Plot.{svg,png,pdf}
    Supplementary_Figure_S5_Shared_Genetic_Architecture.{svg,png,pdf}

  Vector PDFs for submission upload (8 files, `vectorPDF_` prefix, at root):
    vectorPDF_Figure_1_Study_Design_Workflow.pdf … vectorPDF_Supplementary_Figure_S5_Shared_Genetic_Architecture.pdf
```

---

## GitHub repository setup

The package is **already live** at **`https://github.com/Pinellia7ternata/Causal-Inference-1`** (repository is **flat** — all files at the root, no sub-folders; the 8 vector PDFs carry the `vectorPDF_` prefix).

Local working copy is initialised as a git repo. To update from the local package directory:

```bash
cd JAD_Submission_Package_MDD_Anxiety_v2

# If not yet linked:
git remote add origin https://github.com/Pinellia7ternata/Causal-Inference-1.git

# Push updates (default branch is main; use master if yours differs)
git push -u origin main
```

> Note: the WorkBuddy GitHub connector is a GitHub App and must be installed on this repo (Settings → Integrations → Installed GitHub Apps) before it can read/write here. The App **is installed** as of 2026-07-30, so the connector can read (and, with write scope, update) files directly. The git CLI above and the GitHub web UI remain valid fallbacks.

---

## Preview refresh note (WorkBuddy desktop)

If you are previewing `Manuscript_Main_Text_JAD_Revised_v3.docx` inside the WorkBuddy desktop client, **close the preview tab and re-open the file** after figure changes — the preview panel caches rendered images and will not auto-refresh from disk. The on-disk images (verified via `word/media/imageN.png` byte hash) are always up to date with `<name>.png` at the repository root.

---

_Generated: 2026-07-30 · Re-render version v3.1 · Toolchain: resvg-js 0.x + PyMuPDF 1.28.0_