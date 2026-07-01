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


## Step-3: copy fastq files from following folder Or download from the UVa Box folder: [Bioinformatics Workshop](https://virginia.app.box.com/folder/395515355319) provided as the link
<code>
rsync -avPt /project/UVAPK-BX/Bioinformarics_Workshop_2026/fastq_pre-treatment.tar .

rsync -avPt /project/UVAPK-BX/Bioinformarics_Workshop_2026/fastq_post-treatment.tar .
</code>

## Step-4: Download cell-ranger [reference dataset](https://www.10xgenomics.com/support/software/cell-ranger/downloads#reference-downloads)
<code>
wget "https://cf.10xgenomics.com/supp/cell-exp/refdata-gex-GRCh38-2024-A.tar.gz"
</code>

## Step-4: Process pre-treatment fastq files
<code>
tar -xvf fastq_pre-treatment.tar
cd fastq_pre-treatment

cellranger count --id=pretreatment --sample=pretreatment --fastqs=/project/UVABX-PK/Bioinformarics_Workshop_2026/ --transcriptome=/project/UVABX-PK/Bioinformarics_Workshop_2026/pbmc_1k_v3_fastqs/refdata-gex-GRCh38-2024-A --create-bam=false


</code>


## Step-5: Process post-treatment fastq files
<code>
tar -xvf fastq_post-treatment.tar
cd fastq_post-treatment

cellranger count --id=posttreatment --sample=posttreatment --fastqs=/project/UVABX-PK/Bioinformarics_Workshop_2026/ --transcriptome=/project/UVABX-PK/Bioinformarics_Workshop_2026/pbmc_1k_v3_fastqs/refdata-gex-GRCh38-2024-A --create-bam=false


</code>

