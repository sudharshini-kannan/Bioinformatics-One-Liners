# 🧬 Bioinformatics One-Liners & Command-Line Cheatsheet ⚡💻

[![Cheatsheet](https://img.shields.io/badge/Cheatsheet-Bioinformatics-00A86B?style=flat-square)](#-table-of-contents)
[![Linux](https://img.shields.io/badge/CLI-Linux%20%2F%20Bash-0d1117?style=flat-square&logo=linux&logoColor=white)](https://www.gnu.org/software/bash/)
[![Bioinformatics](https://img.shields.io/badge/Field-Bioinformatics-blue?style=flat-square)](https://en.wikipedia.org/wiki/Bioinformatics)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/sudharshini-kannan/Bioinformatics-One-Liners)

A practical collection of **bioinformatics command-line one-liners** for working with common biological data formats and genomic datasets.

This repository provides useful commands for **FASTA, FASTQ, SAM/BAM, VCF**, and text processing using **Linux, Bash, AWK, SED, GREP, SAMtools, and BCFtools**.

---

## 📑 Table of Contents

- [🐧 Linux Commands](#-linux-commands)
- [🧬 FASTA Manipulation](#-fasta-manipulation)
- [📊 FASTQ Processing](#-fastq-processing)
- [🔬 SAM/BAM Operations](#-sambam-operations)
- [🧪 VCF Variant Analysis](#-vcf-variant-analysis)
- [⚡ AWK, SED and GREP](#-awk-sed-and-grep)
- [🛠️ Tools](#️-tools)
- [📂 Repository Structure](#-repository-structure)
- [🎯 Project Goal](#-project-goal)

---

# 🐧 Linux Commands

Common Linux commands useful for navigating and managing bioinformatics projects.

### 1. Check the Current Working Directory

```bash
pwd

Displays the current directory.

2. List Files and Directories
ls -lh

Displays files with detailed information.

3. Find FASTQ Files
find . -name "*.fastq"

Searches recursively for FASTQ files.

4. Check File Sizes
du -sh *

Useful for checking the size of large sequencing datasets.

➡️ More commands: Linux/linux_one_liners.md

🧬 FASTA Manipulation

Useful commands for inspecting and processing FASTA sequence files.

1. Count Sequences in a FASTA File
grep -c "^>" sequences.fasta

Counts FASTA sequence headers.

2. Display FASTA Headers
grep "^>" sequences.fasta

Displays sequence identifiers.

3. Count Total Nucleotides
grep -v "^>" sequences.fasta | tr -d '\n' | wc -c

Counts nucleotide characters in the FASTA file.

➡️ More commands: FASTA/fasta_one_liners.md

📊 FASTQ Processing

Commands for inspecting raw sequencing reads.

1. View the First Sequencing Read
head -4 reads.fastq

A FASTQ record contains four lines.

2. Count Sequencing Reads
wc -l reads.fastq | awk '{print $1/4}'

Calculates the total number of reads.

3. Calculate Average Read Length
awk 'NR%4==2 {sum+=length($0); count++} END {print sum/count}' reads.fastq

Calculates the average sequencing read length.

➡️ More commands: FASTQ/fastq_one_liners.md

🔬 SAM/BAM Operations

Useful commands for working with alignment files.

1. View BAM Alignments
samtools view sample.bam | head

Displays the first alignments in a BAM file.

2. Generate Alignment Statistics
samtools flagstat sample.bam

Provides statistics about mapped and unmapped reads.

3. Sort a BAM File
samtools sort sample.bam -o sample.sorted.bam

Sorts alignments by genomic coordinates.

4. Index a BAM File
samtools index sample.sorted.bam

Creates an index for rapid access to genomic regions.

5. Calculate Average Sequencing Depth
samtools depth sample.sorted.bam | \
awk '{sum+=$3; count++} END {print sum/count}'

Calculates mean sequencing depth.

➡️ More commands: BAM/bam_one_liners.md

🧪 VCF Variant Analysis

Commands for working with genetic variants.

1. View the VCF Header
bcftools view -h variants.vcf

Displays metadata and column headers.

2. Count Variants
bcftools view -H variants.vcf | wc -l

Counts variant records.

3. Extract Chromosome and Position
bcftools query -f '%CHROM\t%POS\n' variants.vcf

Extracts genomic locations.

4. Extract PASS Variants
bcftools view -f PASS variants.vcf

Displays variants that passed filtering.

5. Count SNPs
bcftools view -v snps variants.vcf | \
grep -v "^#" | wc -l

Counts single nucleotide variants.

➡️ More commands: VCF/vcf_one_liners.md

⚡ AWK, SED and GREP

Powerful text-processing commands commonly used in bioinformatics.

1. Print the First Column
awk '{print $1}' file.txt
2. Filter Rows Based on a Value
awk '$3 > 10' file.txt
3. Calculate the Average of a Column
awk '{sum+=$3; count++} END {print sum/count}' file.txt
4. Search for a Pattern
grep "pattern" file.txt
5. Replace Text
sed 's/old/new/g' file.txt

➡️ More commands: AWK_SED/awk_sed_one_liners.md

🛠️ Tools

This project uses common command-line tools:

Linux / Bash
AWK
SED
GREP
SAMtools
BCFtools

📂 Repository Structure

Bioinformatics-One-Liners/
│
├── Linux/
│   └── linux_one_liners.md
│
├── FASTA/
│   └── fasta_one_liners.md
│
├── FASTQ/
│   └── fastq_one_liners.md
│
├── BAM/
│   └── bam_one_liners.md
│
├── VCF/
│   └── vcf_one_liners.md
│
├── AWK_SED/
│   └── awk_sed_one_liners.md
│
└── README.md

🎯 Project Goal

The goal of this project is to create a practical and easy-to-use reference for commonly used bioinformatics command-line operations.

Each section focuses on:

📌 Command
📖 What it does
🧬 Bioinformatics use case
💻 Practical examples

👩‍💻 Author
Sudharshini Kannan
Bioinformatics | Genomics | NGS | Single-Cell Analysis

⭐ This repository is part of my bioinformatics learning journey and portfolio.

🤝 Contributing & Star Requests
If you find this cheatsheet helpful, please Star ⭐ this repository on GitHub! Contributions for new high-performance one-liners are welcome via Pull Requests.
