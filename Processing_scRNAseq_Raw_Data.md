## About the Dataset

There are two tissue biopsy samples belonging to pre-treatment (GSM8086070) and post-treaement (GSM8086066) scRNA-seq from the project "Accession: PRJNA1078290: Immune Re-sensitization in Checkpoint Inhibitor Refractory and Relapsed Cancers with Plinabulin, Radiation and Immune Checkpoint Blockade (human)" which will be processed through cellranger tool and use the results for the downstream analysis using seurat pipeline.

Reference: Lin SH et al., Plinabulin following radiation enhances dendritic cell maturation and checkpoint inhibitor retreatment of relapsed/refractory cancers.", Med, 2025 Oct 10;6(10):100752

|  sample |  fastq name   |   Source    | sample info |
| :---: | :-----------: | :----------:| :----------: |
| 1 | SRR28016090 | GSM8086070 | pre-treatment |
| 2 | SRR28016098 | GSM8086066 | post-treatment |


## Step-1: Login to Rivanna

<code>
ssh computing_id@login.hpc.virginia.edu
</code>

## Step-2: create a directory
<code>
mkdir Bioinformatics_Workshop
cd Bioinformatics_Workshop
</code>


## Step-3: copy cellranger_data.tar.gz file from UVa Box folder: [Bioinformatics Workshop](https://virginia.app.box.com/folder/395515355319) provided as the link
<code>
tar -xvf cellranger_data.tar.gz

</code>

## Step-4: Download cell-ranger [reference dataset](https://www.10xgenomics.com/support/software/cell-ranger/downloads#reference-downloads)
<code>
wget "https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2024-A.tar.gz"
</code>

## Step-5: Copy files to the UVa Rivanna 

<code>
Login to UVa OpenOnDemand Rivanna site

</code>

## Step-6: Process pre-treatment fastq files
<code>
cd cellranger_data/pretreatment

sbatch cellranger.slurm

</code>


## Step-7: Process post-treatment fastq files
<code>
cd cellranger_data/posttreatment

sbatch cellranger.slurm

</code>

