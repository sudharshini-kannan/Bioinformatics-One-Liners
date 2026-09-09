# ⚡ AWK, SED and GREP One-Liners

Useful command-line tools for processing bioinformatics data.

---

# AWK

## 1. Print the first column

```bash
awk '{print $1}' file.txt
2. Print multiple columns
awk '{print $1, $2, $3}' file.txt
3. Filter rows based on a value
awk '$3 > 10' file.txt
4. Calculate the sum of a column
awk '{sum += $3} END {print sum}' file.txt
5. Calculate the average
awk '{sum += $3; count++} END {print sum/count}' file.txt
GREP
6. Search for a pattern
grep "pattern" file.txt
7. Exclude lines containing a pattern
grep -v "pattern" file.txt
8. Count matching lines
grep -c "pattern" file.txt
SED
9. Replace text
sed 's/old/new/g' file.txt
10. Delete empty lines
sed '/^$/d' file.txt