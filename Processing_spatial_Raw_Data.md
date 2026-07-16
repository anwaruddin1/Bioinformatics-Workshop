# Processing Raw Spatial Data with Space Ranger on UVA Rivanna

This page walks through processing raw Visium spatial FASTQ files and a tissue image with Space Ranger on UVA's Rivanna HPC system, producing output ready for downstream analysis in the Seurat pipeline.

## About the Dataset

This workshop uses one FFPE tissue section — **Human Prostate Cancer, Adenocarcinoma with Invasive Carcinoma** — from 10x Genomics' public Visium datasets.

Raw reads will be processed with Space Ranger, and the resulting spot-by-gene matrix (with spatial coordinates and the aligned tissue image) will be used for downstream analysis with the Seurat pipeline.

**Reference:** 10x Genomics. *Human Prostate Cancer, Adenocarcinoma with Invasive Carcinoma (FFPE)*. Space Ranger 1.3.0. Tissue obtained from Indivumed Human Tissue Specimens. [10xgenomics.com/datasets](https://www.10xgenomics.com/datasets/human-prostate-cancer-adenocarcinoma-with-invasive-carcinoma-ffpe-1-standard-1-3-0). Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

| Sample | Dataset Name                        | Source                | Sample Info                                                                 |
| ------ | ------------------------------------ | ---------------------- | ---------------------------------------------------------------------------- |
| 1      | Visium_FFPE_Human_Prostate_Cancer    | 10x Genomics Datasets  | Adenocarcinoma with invasive carcinoma, Stage III, Gleason 7, Slide V11J26-003, Area B1 |

This dataset is a good fit for a workshop because it's probe-based (FFPE), which needs far less sequencing depth than a whole-transcriptome fresh-frozen run — the whole dataset is a single 6.5mm capture area, 4,371 spots under tissue, at a mean of 23,087 reads/spot.

---

## Step 1: Log in to UVA Rivanna

**Option A — OpenOnDemand:** Log in to the [UVA OpenOnDemand Rivanna site](https://ood.hpc.virginia.edu/pun/sys/dashboard) and open a terminal from there.

**Option B — Terminal:** Log in directly via SSH:

```
ssh computing_id@login.hpc.virginia.edu
```

## Step 2: Create a Working Directory

```

mkdir Bioinformatics_Workshop # Skip this step if you have this directory.

cd Bioinformatics_Workshop
mkdir spaceranger_data
cd spaceranger_data
```

## Step 3: Download the Raw Spatial Data

This dataset is hosted directly by 10x Genomics and is CC BY 4.0 licensed — no login or Box relay needed:

```
# Input Files
wget https://cf.10xgenomics.com/samples/spatial-exp/1.3.0/Visium_FFPE_Human_Prostate_Cancer/Visium_FFPE_Human_Prostate_Cancer_fastqs.tar
wget https://cf.10xgenomics.com/samples/spatial-exp/1.3.0/Visium_FFPE_Human_Prostate_Cancer/Visium_FFPE_Human_Prostate_Cancer_image.tif
wget https://cf.10xgenomics.com/samples/spatial-exp/1.3.0/Visium_FFPE_Human_Prostate_Cancer/Visium_FFPE_Human_Prostate_Cancer_Pathologist_Annotations.png

```

Extract the FASTQs:

```
tar -xvf Visium_FFPE_Human_Prostate_Cancer_fastqs.tar
```

> Note: confirm the tissue image's exact file extension on the [dataset's Input files tab](https://www.10xgenomics.com/datasets/human-prostate-cancer-adenocarcinoma-with-invasive-carcinoma-ffpe-1-standard-1-3-0) before running — it's expected to be `.jpg`, but Space Ranger accepts `.jpg`, `.tif`, or `.png` equally, so only the filename below would need to change.

## Step 4: Download the Space Ranger Reference and Probe Set

Skip this if you already have the Human reference data from cell ranger run.
Move back up to the working directory first:

```
cd ..
```

Download the [reference transcriptome](https://www.10xgenomics.com/support/software/space-ranger/downloads#reference-downloads):

```
wget "https://cf.10xgenomics.com/supp/spatial-exp/refdata-gex-GRCh38-2020-A.tar.gz"
tar -zxvf refdata-gex-GRCh38-2020-A.tar.gz
```

This dataset is FFPE (probe-based), so Space Ranger also needs the matching human probe set:

```
wget "https://cf.10xgenomics.com/samples/spatial-exp/1.3.0/Visium_FFPE_Human_Prostate_Cancer/Visium_FFPE_Human_Prostate_Cancer_probe_set.csv"
```

## Step 5: Process the Sample with Space Ranger

```
cd spaceranger_data
sbatch spaceranger.slurm
```

`spaceranger.slurm` wraps the following command:

```
spaceranger count \
  --id=Visium_FFPE_Human_Prostate_Cancer \
  --transcriptome=../refdata-gex-GRCh38-2020-A \
  --probe-set=../Visium_Human_Transcriptome_Probe_Set_v1.0_GRCh38-2020-A.csv \
  --fastqs=Visium_FFPE_Human_Prostate_Cancer_fastqs \
  --image=Visium_FFPE_Human_Prostate_Cancer_image.jpg \
  --slide=V11J26-003 \
  --area=B1 \
  --create-bam=false
```

---

Once the job completes, check `outs/web_summary.html` first to confirm spots were called under tissue and QC metrics look reasonable. The Space Ranger output (filtered feature-barcode matrix, spatial coordinates, and aligned tissue image) will then be ready for import into the Seurat pipeline (`Load10X_Spatial()`) for downstream analysis.
