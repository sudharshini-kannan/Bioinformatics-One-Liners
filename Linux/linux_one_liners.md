# 🐧 Linux One-Liners for Bioinformatics

Useful Linux commands for navigating files, inspecting data, and managing bioinformatics projects.

---

## 1. Check the current directory

### Command

```bash
pwd
Description

Displays the current working directory.

Bioinformatics use case

Useful for confirming your location before running an analysis pipeline.

2. List files
Command
ls
Description

Lists files and directories.

3. List files with details
Command
ls -lh
Description

Displays file permissions, sizes, and modification dates.

4. Count the number of files
Command
ls | wc -l
Description

Counts the number of files and directories.

5. Check disk usage
Command
du -sh *
Description

Displays the size of files and directories.

Bioinformatics use case

Useful for checking the size of large sequencing files.

6. Search for a file
Command
find . -name "*.fastq"
Description

Finds all FASTQ files in the current directory and subdirectories.

7. View the first lines of a file
Command
head file.txt
8. View the last lines of a file
Command
tail file.txt
9. Count lines in a file
Command
wc -l file.txt
10. Search for text
Command
grep "pattern" file.txt
Bioinformatics use case

Useful for searching headers, chromosome names, genes, or variants.