# NGS_Data_Preprocessing_Pipeline_Quality_Control_and_Trimming_NCBI_SRA_ID_SRR531365
NGS_Data_Preprocessing_Pipeline_Quality_Control_and_Trimming_NCBI_SRA_ID_SRR531365
# 📉 NGS Data Preprocessing Pipeline: QC and Trimming (SRR531365)

This repository contains a comprehensive **Jupyter Notebook** pipeline that demonstrates the essential steps for preprocessing raw **Next-Generation Sequencing (NGS)** data. The workflow uses a specific RNA-Seq accession (**SRR531365**) from the NCBI SRA database for demonstration, focusing on **Quality Control (QC)** using **FastQC** and subsequent **Trimming** using **Trimmomatic**.

This pipeline ensures raw sequencing reads are clean and of high quality before proceeding to downstream analysis like alignment or differential expression.

## 🚀 Key Features

* **End-to-End Preprocessing:** Covers data fetching, QC analysis, and read trimming in a single, executable notebook.
* **Toolchain Setup:** Automatically installs necessary bioinformatics tools: **sra-toolkit**, **FastQC**, and **Trimmomatic**.
* **Data Retrieval:** Downloads raw reads directly from the **SRA database** using the `sra-toolkit`.
* **Quality Control (FastQC):** Runs FastQC on both the **raw** and **trimmed** FASTQ files, allowing for visual confirmation of quality improvement (reports are generated in HTML format).
* **Adapter and Quality Trimming (Trimmomatic):** Executes Trimmomatic to remove Illumina adapters and trim low-quality bases using optimized parameters.
* **Output Analysis:** Provides commands to inspect the size and read count of the trimmed FASTQ file, confirming successful preprocessing.

---

## 🔬 Workflow Steps

The notebook is structured into the following executable steps:

1.  **Setup and Installation:** Installs Java (required by Trimmomatic), `sra-toolkit`, `FastQC`, and `Trimmomatic`.
2.  **Data Download:** Fetches and converts the raw SRA accession **SRR531365** into a single-end FASTQ file.
3.  **Initial Quality Control (FastQC):** Runs FastQC on the **raw** FASTQ file to generate an initial QC report.
4.  **Read Trimming (Trimmomatic):** Executes Trimmomatic with parameters for:
    * **Adapter removal** (`ILLUMINACLIP`).
    * **Leading/Trailing low-quality base removal** (quality $< 3$).
    * **Sliding window quality filtering** (window size 4, average quality 15).
    * **Minimum read length** (36 bp).
5.  **Post-Trimming QC:** Runs FastQC on the **trimmed** FASTQ file to assess the improvement in read quality.
6.  **Inspection and Download:** Checks file sizes and provides commands for downloading the final trimmed FASTQ files.

---

## 🛠️ Prerequisites and Execution

### Requirements

To run this pipeline, you need a Python environment (like Google Colab or JupyterLab) with access to a Linux terminal and the following tools (which the script installs):

* **`Java`** (for Trimmomatic)
* **`sra-toolkit`** (for `prefetch` and `fasterq-dump`)
* **`FastQC`**
* **`Trimmomatic`**

### How to Run

1.  Open the **`NGS_Data_Preprocessing_Pipeline_Quality_Control_and_Trimming_NCBI_SRA_ID_SRR531365.ipynb`** file in Google Colab or a Jupyter environment.
2.  Execute all cells sequentially.

---

## 📁 Output Files

The pipeline generates the following key files in the execution directory:

| Filename | Format | Tool | Description |
| :--- | :--- | :--- |
| `SRR531365.fastq` | FASTQ | sra-toolkit | The **raw** sequence read file. |
| `SRR531365_fastqc.html` | HTML | FastQC | **Initial QC report** on the raw reads. |
| `SRR531365_trimmed.fastq` | FASTQ | Trimmomatic | The **cleaned and trimmed** sequence read file (ready for alignment). |
| `SRR531365_trimmed_fastqc.html` | HTML | FastQC | **Post-trimming QC report** (should show improved quality). |
