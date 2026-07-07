## About the Dataset

There are two tissue biopsy samples belonging to pre-treatment (GSM8086070) and post-treaement (GSM8086066) scRNA-seq which will be processed through cellranger tool and use the results for the downstream analysis using seurat pipeline.

|  sample |  fastq name   |   Source    |
| :---: | :-----------: | :----------:|
| 1 | SRR28016090 | GSM8086070 |
| 2 | SRR28016098 | GSM8086066 |


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
gunzip cellranger_data.tar.gz

</code>

## Step-4: Download cell-ranger [reference dataset](https://www.10xgenomics.com/support/software/cell-ranger/downloads#reference-downloads)
<code>
wget "https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2024-A.tar.gz"
</code>

## Step-5: Process pre-treatment fastq files
<code>
cd cellranger_data/pretreatment

sbatch cellranger.slurm

</code>


## Step-6: Process post-treatment fastq files
<code>
cd cellranger_data/pretreatment

sbatch cellranger.slurm

</code>

