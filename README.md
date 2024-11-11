# Pea
```
/mnt2/results/20241017_GBS_sunflower/call_all/Pea$ time vcftools --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf --maf 0.01 --max-missing 0.95 --recode --out Pea_short_filt_maf0.01_max-missing0.95

VCFtools - v0.1.12b
(C) Adam Auton and Anthony Marcketta 2009

Parameters as interpreted:
        --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf
        --maf 0.01
        --max-missing 0.95
        --out Pea_short_filt_maf0.01_max-missing0.95
        --recode

After filtering, kept 6 out of 6 Individuals
Outputting VCF file...
After filtering, kept 69906 out of a possible 163975716 Sites
Run Time = 475.00 seconds

real    7m55.338s
user    7m49.578s
sys     0m5.704s
```
Файл Pea_short_filt_maf0.01_max-missing0.95.recode.vcf перенесен с новой сборки на старую:
```
(snplift_env) erofeevan@novaplant1:/mnt/users/erofeevan/Plant_culture/Sunflower/snplift$ time ./snplift 02_infos/snplift_config.sh
# Input files
export OLD_GENOME="/mnt/reference/genomes/pisum_sativum/GCF_024323335.1/GCF_024323335.1_CAAS_Psat_ZW6_1.0_genomic.unmasked.fna"
export NEW_GENOME="/mnt/users/erofeevan/Plant_culture/Pea/Pisum_sativum_v1a.fa"
# Output files
export INPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short_filt_maf0.01_max-missing0.95.recode.vcf"
export OUTPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_filt_short_Psat_ZW6_1.0.vcf"
```
