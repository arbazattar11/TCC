# TCC Analysis Pipeline

This pipeline is designed to analyze TCC data, which integrates chromatin conformation data (e.g., Hi-C) with transcriptomic data (e.g., RNA-seq). Below are the steps involved:

1. **Quality Control (QC) for RNA-seq Data:**
   - FASTQ files are checked for quality using FastQC, and a summary report is generated using MultiQC.

2. **Alignment of RNA-seq Reads:**
   - Reads are aligned to the reference genome using HISAT2, and sorted BAM files are generated using samtools.

3. **Transcript Quantification:**
   - Transcript abundances are estimated using StringTie based on the aligned RNA-seq reads.

4. **Quality Control for Hi-C Data:**
   - Perform QC for Hi-C data if available.

5. **Hi-C Data Processing and Analysis:**
   - Process and analyze Hi-C data using Hi-C specific tools like HiC-Pro.

6. **Integration of Hi-C and RNA-seq Data:**
   - Integrate Hi-C and RNA-seq data using TCC-specific tools like TCC-GUI.

7. **Differential Gene Expression Analysis:**
   - Perform differential gene expression analysis using tools like DESeq2 or edgeR.

8. **Correlation Analysis between Chromatin Structure and Gene Expression:**
   - Perform correlation analysis between Hi-C interaction frequencies and gene expression levels.

9. **Visualization and Interpretation:**
   - Visualize and interpret the integrated TCC data to gain insights into the relationship between chromatin structure and gene expression.

## Usage
- Clone this repository.
- Place your RNA-seq FASTQ files and Hi-C data in the same directory as the pipeline script.
- Modify the script as necessary to specify paths and parameters.
- Run the pipeline using `./pipeline.sh`.

## Requirements
- HISAT2
- Samtools
- StringTie
- Hi-C specific tools (e.g., HiC-Pro)
- TCC-specific tools (e.g., TCC-GUI)
- Differential gene expression analysis tools (e.g., DESeq2, edgeR)

## Notes
- Adjust parameters and additional analysis steps based on specific experimental needs.
- Ensure reference genome files are available and properly indexed.
