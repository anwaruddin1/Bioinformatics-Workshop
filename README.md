# Single-Cell and Spatial Transcriptomics Data Analyis Workshop

**UVA Bioinformatics Core — 3-Day Hands-On Training Program**

![UVA Bioinformatics Core](https://img.shields.io/badge/UVA-Bioinformatics%20Core-232D4B?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-E57200?style=flat-square)
![R](https://img.shields.io/badge/R-Seurat-blue?style=flat-square)

Materials, notebooks, code, and datasets for the UVA Bioinformatics Core's **Single-Cell and Spatial Transcriptomics** workshop — a 3-day, hands-on-intensive training program in scRNA-seq and spatial transcriptomics data analysis.

---

## Table of Contents

- [Overview](#overview)
- [Learning Objectives](#learning-objectives)
- [Target Audience & Prerequisites](#target-audience--prerequisites)
- [Repository Structure](#repository-structure)
- [Setup Instructions](#setup-instructions)
- [Schedule](#schedule)
  - [Day 1: Introduction to Single-Cell RNA-seq](#day-1-introduction-to-single-cell-rna-seq)
  - [Day 2: Downstream Analysis, Annotation & Dynamics](#day-2-downstream-analysis-annotation--dynamics)
  - [Day 3: Spatial Transcriptomics](#day-3-spatial-transcriptomics)
- [Key Topics](#key-topics)
- [Datasets](#datasets)
- [Abbreviations](#abbreviations)
- [Contact](#contact)

---

## Overview

This workshop provides intensive, hands-on training in the analysis of single-cell RNA sequencing (scRNA-seq) and spatial transcriptomics data for researchers, students, and laboratory personnel at UVA. Participants learn the foundations of single-cell and spatial transcriptomics technologies, then move quickly into computational practice: quality control, integration, normalization, clustering, cell type annotation, trajectory inference, cell-cell communication analysis, and spatial data processing.

The majority of each day is spent working directly in **R (Seurat)** on real datasets, using cloud-based compute (UVA Research Computing / Rivanna and Google Colab), so participants leave with working, reusable analysis code rather than slides alone.

| | |
|---|---|
| **Format** | Lecture + Hands-on Lab (hands-on emphasis) |
| **Duration** | 3 Days |
| **Morning** | 9:00 – 10:00 AM Lecture |
| **Afternoon / Lab** | 10:15 AM – 4:00 PM Hands-on Lab |

---

## Learning Objectives

By the end of this workshop, participants will be able to:

- Describe the experimental principles of single-cell RNA-seq (droplet-based, plate-based) and spatial transcriptomics (imaging-based and sequencing-based) platforms
- Perform quality control and preprocessing of single-cell count data, including filtering by UMI counts, gene counts, and mitochondrial content, ambient RNA correction, and doublet detection
- Execute standard downstream analysis workflows: integration, normalization, dimensionality reduction (PCA, UMAP/t-SNE), clustering, and marker gene identification using Seurat
- Annotate cell types using marker-based and reference-based (label transfer) approaches, and perform differential expression testing between conditions or clusters
- Apply trajectory inference and cell-cell communication analysis to interpret dynamic and interactive cellular processes
- Process, QC, and analyze spatial transcriptomics data (e.g., 10x Visium, Xenium), including spot/cell deconvolution and integration with matched scRNA-seq datasets
- Apply reproducibility and reporting best practices for single-cell and spatial studies, including data/code sharing and standardized metadata

---

## Target Audience & Prerequisites

**Who this is for:**
- Graduate students, postdocs, and research staff planning to generate or analyze single-cell or spatial transcriptomics data
- Current wet-lab researchers who want to develop a working computational foundation in scRNA-seq/spatial analysis, including comfort with R
- Investigators designing future single-cell or spatial transcriptomics experiments
- Bioinformatics staff and core facility personnel seeking a refresher on current single-cell/spatial tools and best practices

**Prerequisites:** Basic familiarity with R and the command line is recommended but not mandatory. No prior single-cell analysis experience required. Participants should bring a laptop.



## Repository Structure# Single-Cell RNA-seq Data Analysis

├── day1_intro_scRNAseq/
│   ├── notebooks/
│   ├── data/
│   └── README.md
├── day2_annotation_dynamics/
│   ├── notebooks/
│   ├── data/
│   └── README.md
├── day3_spatial_transcriptomics/
│   ├── notebooks/
│   ├── data/
│   └── README.md
├── environment/
│   ├── renv.lock
│   └── setup.R
└── README.md

> Adjust the tree above to match your actual folder layout.

---

## Setup Instructions

1. Clone this repository:
```bash
   git clone https://github.com/<your-org>/<your-repo>.git
   cd <your-repo>
```
2. Install R (≥ 4.3) and RStudio, or use the provided cloud notebook environment (UVA Rivanna / Google Colab link — *add link here*).
3. Restore the R environment:
```r
   install.packages("renv")
   renv::restore()
```
4. Launch the Day 1 notebook to confirm your setup:
```r
   rmarkdown::render("day1_intro_scRNAseq/notebooks/00_setup_check.Rmd")
```

---

## Schedule

### Day 1: Introduction to Single-Cell RNA-seq
*Technology Overview · QC & Preprocessing · First Clustering*

| Time | Activity |
|---|---|
| 9:00 – 10:00 AM | Lecture |
| 10:00 – 10:15 AM | Break |
| 10:15 AM – 12:00 PM | Lab Part 1 — Environment setup, data loading, QC filtering, ambient correction, doublet detection |
| 12:00 – 12:30 PM | Lunch |
| 12:30 – 4:00 PM | Lab Part 2 — Integration, normalization, clustering, UMAP |

### Day 2: Downstream Analysis, Annotation & Dynamics
*Cell Type Annotation · Differential Expression · Trajectory Inference · Cell–Cell Communication*

| Time | Activity |
|---|---|
| 9:00 – 10:00 AM | Lecture |
| 10:00 – 10:15 AM | Break |
| 10:15 AM – 12:00 PM | Lab Part 1 — Annotation and differential expression |
| 12:00 – 12:30 PM | Lunch |
| 12:30 – 4:00 PM | Lab Part 2 — Trajectory inference and cell–cell communication (NicheNet) |

### Day 3: Spatial Transcriptomics
*Platform Overview · Spatial QC · Deconvolution · Integration with scRNA-seq · Final Project*

| Time | Activity |
|---|---|
| 9:00 – 10:00 AM | Lecture |
| 10:00 – 10:15 AM | Break |
| 10:15 AM – 12:00 PM | Lab Part 1 — Spatial data QC and processing |
| 12:00 – 12:30 PM | Lunch |
| 12:30 – 3:30 PM | Lab Part 2 — Deconvolution, integration, and figures |
| 3:30 – 4:00 PM | Group project presentations, Q&A, certificate distribution |

---

## Key Topics

- Introduction to single-cell RNA-seq and spatial transcriptomics platforms (Day 1)
- Single-cell data QC, filtering, and preprocessing in Seurat (Day 1)
- Integration, normalization, dimensionality reduction, clustering, and marker gene identification (Day 1–2)
- Cell type annotation, differential expression, and multi-sample/condition comparisons (Day 2)
- Trajectory inference and cell-cell communication analysis (Day 2)
- Spatial transcriptomics platforms, QC, and processing — 10x Visium and Xenium (Day 3)
- Spot/cell deconvolution, marker analysis, and cell type annotation in spatial data (Day 3)
- Pseudo-bulk analysis, cell-cell communication, and spatial visualization (Day 3)

---

## Datasets

| Dataset | Platform | Used In | Link |
|---|---|---|---|
| PBMC 10x dataset | 10x Chromium | Day 1–2 | *add link* |
| Differentiation time-course | 10x Chromium | Day 2 (trajectory) | *add link* |
| Visium/Xenium tissue dataset | 10x Visium / Xenium | Day 3 | *add link* |

---

## Abbreviations

| Term | Definition | Term | Definition |
|---|---|---|---|
| scRNA-seq | Single-Cell RNA Sequencing | UMAP | Uniform Manifold Approximation and Projection |
| PCA | Principal Component Analysis | t-SNE | t-Distributed Stochastic Neighbor Embedding |
| UMI | Unique Molecular Identifier | QC | Quality Control |
| DE | Differential Expression | SCT | SCTransform (normalization method) |
| HVG | Highly Variable Genes | FFPE | Formalin-Fixed Paraffin-Embedded (tissue) |

---

## Contact

**UVA Bioinformatics Core**
📍 *Room/Building — add location*
✉️ *add contact email*
🌐 *add core website link*

---

*Materials developed and maintained by the UVA Bioinformatics Core. For educational use.*





### Raw Data Processing using CellRanger
([`Processing_scRNAseq_Raw_Data`](Processing_scRNAseq_Raw_Data.md))

### Downstream Analyiss using Seurat Pipeline
([`Downstream_scRNAseq_Seurat_Pipeline`](Downstream_scRNAseq_Seurat_Pipeline.md))


# Processing of Raw spatial Data
([`Processing_spatial_Raw_Data.md`](Processing_spatial_Raw_Data.md))



