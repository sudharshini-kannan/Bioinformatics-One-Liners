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

Common Linux commands useful for bioinformatics projects.

| # | Task | Command |
|---|---|---|
| 1 | Check current directory | `pwd` |
| 2 | List files with details | `ls -lh` |
| 3 | Find FASTQ files | `find . -name "*.fastq"` |
| 4 | Check file sizes | `du -sh *` |
| 5 | Count lines in a file | `wc -l file.txt` |
| 6 | Search for text | `grep "pattern" file.txt` |

📖 **Detailed commands:** [Linux One-Liners →](Linux/linux_one_liners.md)

---

# 🧬 FASTA Manipulation

Useful commands for inspecting and processing FASTA files.

| # | Task | Command |
|---|---|---|
| 1 | Count sequences | `grep -c "^>" sequences.fasta` |
| 2 | Display headers | `grep "^>" sequences.fasta` |
| 3 | Count total nucleotides | `grep -v "^>" sequences.fasta \| tr -d '\n' \| wc -c` |

📖 **Detailed commands:** [FASTA One-Liners →](FASTA/fasta_one_liners.md)

---

# 📊 FASTQ Processing

Useful commands for inspecting sequencing reads.

| # | Task | Command |
|---|---|---|
| 1 | View first sequencing read | `head -4 reads.fastq` |
| 2 | Count sequencing reads | `wc -l reads.fastq \| awk '{print $1/4}'` |
| 3 | View first 10 reads | `head -40 reads.fastq` |
| 4 | Extract read identifiers | `awk 'NR%4==1' reads.fastq` |
| 5 | Calculate average read length | `awk 'NR%4==2 {sum+=length($0); count++} END {print sum/count}' reads.fastq` |

📖 **Detailed commands:** [FASTQ One-Liners →](FASTQ/fastq_one_liners.md)

---

# 🔬 SAM/BAM Operations

Useful SAMtools commands for alignment files.

| # | Task | Command |
|---|---|---|
| 1 | View BAM alignments | `samtools view sample.bam \| head` |
| 2 | View BAM header | `samtools view -H sample.bam` |
| 3 | Count alignments | `samtools view -c sample.bam` |
| 4 | Alignment statistics | `samtools flagstat sample.bam` |
| 5 | Sort BAM file | `samtools sort sample.bam -o sample.sorted.bam` |
| 6 | Index BAM file | `samtools index sample.sorted.bam` |
| 7 | Calculate depth | `samtools depth sample.sorted.bam` |

📖 **Detailed commands:** [BAM One-Liners →](BAM/bam_one_liners.md)

---

# 🧪 VCF Variant Analysis

Useful BCFtools commands for variant analysis.

| # | Task | Command |
|---|---|---|
| 1 | View VCF header | `bcftools view -h variants.vcf` |
| 2 | Count variants | `bcftools view -H variants.vcf \| wc -l` |
| 3 | Extract chromosome and position | `bcftools query -f '%CHROM\t%POS\n' variants.vcf` |
| 4 | Extract PASS variants | `bcftools view -f PASS variants.vcf` |
| 5 | Count SNPs | `bcftools view -v snps variants.vcf` |
| 6 | Count INDELs | `bcftools view -v indels variants.vcf` |

📖 **Detailed commands:** [VCF One-Liners →](VCF/vcf_one_liners.md)

---

# ⚡ AWK, SED and GREP

Powerful tools for processing bioinformatics data.

| # | Task | Command |
|---|---|---|
| 1 | Print first column | `awk '{print $1}' file.txt` |
| 2 | Filter rows | `awk '$3 > 10' file.txt` |
| 3 | Calculate sum | `awk '{sum+=$3} END {print sum}' file.txt` |
| 4 | Calculate average | `awk '{sum+=$3; count++} END {print sum/count}' file.txt` |
| 5 | Search pattern | `grep "pattern" file.txt` |
| 6 | Exclude pattern | `grep -v "pattern" file.txt` |
| 7 | Replace text | `sed 's/old/new/g' file.txt` |

📖 **Detailed commands:** [AWK/SED One-Liners →](AWK_SED/awk_sed_one_liners.md)

---
🛠️ Tools

This project uses common command-line tools:

Linux / Bash
AWK
SED
GREP
SAMtools
BCFtools

# 📂 Repository Structure

```text
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

---

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
