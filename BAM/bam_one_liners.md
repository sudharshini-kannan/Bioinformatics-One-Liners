# 🔬 BAM/SAM One-Liners

Useful SAMtools commands for working with alignment files.

---

## 1. View a BAM file

### Command

```bash
samtools view sample.bam | head
2. View BAM header
Command
samtools view -H sample.bam
3. Count aligned reads
Command
samtools view -c sample.bam
4. Generate alignment statistics
Command
samtools flagstat sample.bam
Bioinformatics use case

Provides alignment statistics including mapped and unmapped reads.

5. Sort a BAM file
Command
samtools sort sample.bam -o sample.sorted.bam
6. Index a BAM file
Command
samtools index sample.sorted.bam
7. Check sequencing depth
Command
samtools depth sample.sorted.bam
8. Calculate average sequencing depth
Command
samtools depth sample.sorted.bam | awk '{sum+=$3; count++} END {print sum/count}'