## About the Dataset

There are two tissue biopsy samples belonging to pre-treatment (GSM8086070) and post-treaement (GSM8086066) scRNA-seq which will be processed through cellranger tool and use the results for the downstream analysis using seurat pipeline.

|  file |  fastq name   |   Source    |
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


## Step-3: copy fastq files from following folder Or download from the UVa Box provided as the link
<code>
rsync -avPt /project/UVAPK-BX/Bioinformarics_Workshop_2026/fastq_pre-treatment.tar .

rsync -avPt /project/UVAPK-BX/Bioinformarics_Workshop_2026/fastq_post-treatment.tar .
</code>



