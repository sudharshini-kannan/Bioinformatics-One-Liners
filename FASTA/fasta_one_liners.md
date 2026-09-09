# 🧬 FASTA One-Liners

Useful commands for working with FASTA sequence files.

---

## 1. Count sequences in a FASTA file

### Command

```bash
grep -c ">" sequences.fasta
Description

Counts the number of sequence headers.

2. Display FASTA headers
Command
grep ">" sequences.fasta
3. Display the first FASTA header
Command
grep ">" sequences.fasta | head -1
4. Count nucleotide characters
Command
grep -v ">" sequences.fasta | tr -d '\n' | wc -c
Description

Counts the total number of nucleotide bases.

5. Extract FASTA headers
Command
grep "^>" sequences.fasta
6. Count sequences with headers
Command
grep "^>" sequences.fasta | wc -l