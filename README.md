# About haploRILs
- Title: haploRILs.R
- Author: jmontero
- Date: 2024-10-11
- Description: Founder haploblock reconstruction: (1) Converts heterozygous sites to missing calls, (2) Compares each progeny (RIL/DH) with all founders and creates score matrix with 0/1 scores per SNP and founder based on similarity to each founder, (3) Bin scores by sliding windows of window size 'nSnp' and overlap 'step', (4) Detect highest-scoring founder, (5) Build haploblocks based on contiguous windows assigned to same founder, (6) Validate putative crossovers by comparing the highest-scoring founders between the CO by comparing 'K' context regions before and after these, (7) Merge dissenting isolated haploblocks, (8) Return the haploblock pedigree information, score details and coordinates.
- Usage: ./haploRILs.R filename nSnp step K number_founders
- Input: PED/MAP called <filename>. The PED has individual by rows, individual ID in first col and SNP allele in the rest, with founders followed by descendants. The alleles are denoted by the numbers 1 and 2 (genotypes would be 1 1/1 2/2 2). Missing genotype = 9. The MAP file has SNPs by rows and chromosome and physical distance by columns. The number of cols in PED should be (number of rows in MAP file)*2 + 1
- Output: filepath_nSnp_step_K.hbk (haploblocks)
- Remarks: Now allows to set up the minimum number of SNPs per window based on the aim resolution. Step as input

