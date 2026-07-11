# Single-Cell and Spatial Transcriptomics Workshop

**UVA Bioinformatics Core — 3-Day Hands-On Training Program**

![UVA Bioinformatics Core](https://img.shields.io/badge/UVA-Bioinformatics%20Core-232D4B?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-E57200?style=flat-square)
![R](https://img.shields.io/badge/R-Seurat-blue?style=flat-square)

Materials, notebooks, code, and datasets for the UVA Bioinformatics Core's **Single-Cell and Spatial Transcriptomics** workshop — a 3-day, hands-on-intensive training program in scRNA-seq and spatial transcriptomics analysis using R (Seurat).

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

---

## Repository Structure# Single-Cell RNA-seq Data Analysis
### Raw Data Processing using CellRanger
([`Processing_scRNAseq_Raw_Data`](Processing_scRNAseq_Raw_Data.md))

### Downstream Analyiss using Seurat Pipeline
([`Downstream_scRNAseq_Seurat_Pipeline`](Downstream_scRNAseq_Seurat_Pipeline.md))


# Processing of Raw spatial Data
([`Processing_spatial_Raw_Data.md`](Processing_spatial_Raw_Data.md))



