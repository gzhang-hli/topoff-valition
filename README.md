# Topoff-valition
# 
This repo provides scripts comparing VCF files for genotype concordance. One usage of the scripts is for validating two sequencing runs that belong to the same sample/individual.

# Required to install tools
aws_s3_cli
bedtools
bcftools 
tabix 
bgzip

# Required auxiliary files in share folder
giab.hg38.bed 
genentech.vcf.header

# Usage one:
compare a pair of VCF files that are generated either from GATK/genentech or from Isaac variant caller (IVC). Currently we use 95% of genotype/marker concordance as the "PASS" validtion threshold. Any concordance number below 95% is considered "FAIL" valition. 

test_one_pair_gatk_ivc.hg38.sh  sample_key1 sample_key2

input args: sampleID1_executionID2 sampleID2_executionID2

stdout: PCT_Concordance1 PCT_Concordance2 Max_Concordance Validation_status

Example run:
test_one_pair_gatk_ivc.hg38.sh 201895694_460283 176501434_459111

stdout: 61.46 60.28 61.46 FAIL
