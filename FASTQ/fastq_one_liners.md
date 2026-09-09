# 📊 FASTQ One-Liners

Useful commands for inspecting FASTQ sequencing files.

---

## 1. View the first sequencing read

### Command

```bash
head -4 reads.fastq
Description

A FASTQ read consists of four lines.

2. Count the number of reads
Command
wc -l reads.fastq | awk '{print $1/4}'
Description

Each sequencing read occupies four lines.

3. View the first 10 reads
Command
head -40 reads.fastq
4. View sequence identifiers
Command
awk 'NR%4==1' reads.fastq
5. Extract sequences
Command
awk 'NR%4==2' reads.fastq
6. Calculate the average read length
Command
awk 'NR%4==2 {sum+=length($0); count++} END {print sum/count}' reads.fastq