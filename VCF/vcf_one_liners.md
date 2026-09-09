# 🧪 VCF One-Liners

Useful commands for working with Variant Call Format (VCF) files.

---

## 1. View VCF header

### Command

```bash
bcftools view -h variants.vcf
2. Count variants
Command
bcftools view -H variants.vcf | wc -l
3. View the first variants
Command
bcftools view variants.vcf | head
4. Extract chromosome and position
Command
bcftools query -f '%CHROM\t%POS\n' variants.vcf
5. Extract variant information
Command
bcftools query -f '%CHROM\t%POS\t%REF\t%ALT\n' variants.vcf
6. Extract PASS variants
Command
bcftools view -f PASS variants.vcf
7. Count SNPs
Command
bcftools view -v snps variants.vcf | grep -v "^#" | wc -l
8. Count INDELs
Command
bcftools view -v indels variants.vcf | grep -v "^#" | wc -l