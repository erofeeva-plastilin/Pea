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
export OUTPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_filt_short_v1a.vcf"
```
```
SNPLift: Extract features from alignments

SNPLift: Skipping visualization

SNPLift: Score markers based on extracted features

SNPLift: Getting coordinates of transferable SNPs

SNPLift: Writing output file with updated coordinates

SNPLift: Number of SNPs treated at each step

69840   Positions
69840   Scores
69281   Transferable

SNPLift: Percentage of transferred SNPs:

99.1995%

SNPLift: Run completed

End: 20241111_085854

real    2m30.087s
user    1m24.746s
sys     0m56.770s
```
Фильтрация только нужных позиций
```
bgzip Pea_filt_short_v1a.vcf
tabix --csi -p vcf Pea_filt_short_v1a.vcf.gz
bcftools view -R pos.txt Pea_filt_short_v1a.vcf.gz -o Pea_target_pos_v1a.vcf
```
Мало snp найдено (Pea_target_pos_v1a.vcf) - 11

```
/mnt2/results/20241017_GBS_sunflower/call_all/Pea$ time vcftools --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf --maf 0.01 --recode --out Pea_short_filt_maf0.01

VCFtools - v0.1.12b
(C) Adam Auton and Anthony Marcketta 2009

Parameters as interpreted:
        --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf
        --maf 0.01
        --out Pea_short_filt_maf0.01
        --recode

After filtering, kept 6 out of 6 Individuals
Outputting VCF file...
After filtering, kept 396303 out of a possible 163975716 Sites
Run Time = 446.00 seconds

real    7m25.785s
user    7m21.510s
sys     0m4.256s
```
Файл Pea_short_filt_maf0.01.recode.vcf перенесен с новой сборки на старую:
```
(snplift_env) erofeevan@novaplant1:/mnt/users/erofeevan/Plant_culture/Sunflower/snplift$ time ./snplift 02_infos/snplift_config.sh
# Input files
export OLD_GENOME="/mnt/reference/genomes/pisum_sativum/GCF_024323335.1/GCF_024323335.1_CAAS_Psat_ZW6_1.0_genomic.unmasked.fna"
export NEW_GENOME="/mnt/users/erofeevan/Plant_culture/Pea/Pisum_sativum_v1a.fa"
# Output files
export INPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short_filt_maf0.01.recode.vcf"
export OUTPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_filt_short_maf0.01_v1a_part2.vcf"
SNPLift: Number of SNPs treated at each step

396124  Positions
396016  Scores
373920  Transferable

SNPLift: Percentage of transferred SNPs:

94.3946%

SNPLift: Run completed

End: 20241111_100454

real    17m13.203s
user    16m33.424s
sys     0m53.049s
```
Фильтрация только нужных позиций
```
bgzip Pea_filt_short_maf0.01_v1a_part2.vcf
tabix --csi -p vcf Pea_filt_short_maf0.01_v1a_part2.vcf.gz
bcftools view -R pos.txt Pea_filt_short_maf0.01_v1a_part2.vcf.gz -o Pea_target_pos_v1a_part2.vcf
```
Мало snp найдено (Pea_target_pos_v1a_part2.vcf) - 25

```
time vcftools --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf --maf 0.001 --recode --out Pea_short_filt_maf0.001
Parameters as interpreted:
        --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf
        --maf 0.001
        --out Pea_short_filt_maf0.001
        --recode

After filtering, kept 6 out of 6 Individuals
Outputting VCF file...
After filtering, kept 396303 out of a possible 163975716 Sites
Run Time = 459.00 seconds

real    7m38.667s
user    7m33.572s
sys     0m5.072s
```
Ничего не изменилось
```
time vcftools --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf --maf 0.0001 --recode --out Pea_short_filt_maf0.0001
Parameters as interpreted:
        --vcf /mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_short.vcf
        --maf 0.0001
        --out Pea_short_filt_maf0.0001
        --recode

After filtering, kept 6 out of 6 Individuals
Outputting VCF file...
After filtering, kept 396303 out of a possible 163975716 Sites
Run Time = 457.00 seconds

real    7m37.251s
user    7m32.207s
sys     0m4.992s
```
И тут ничего не изменилось

Будем переносить 25 SNP
```
time ./snplift 02_infos/snplift_config.sh
export OLD_GENOME="/mnt/users/erofeevan/Plant_culture/Pea/Pisum_sativum_v1a.fa"
export NEW_GENOME="/mnt/reference/genomes/pisum_sativum/GCF_024323335.1/GCF_024323335.1_CAAS_Psat_ZW6_1.0_genomic.unmasked.fna"
# Output files
export INPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_target_pos_v1a_part2.vcf"
export OUTPUT_FILE="/mnt2/results/20241017_GBS_sunflower/call_all/Pea/Pea_final.vcf"

SNPLift: Number of SNPs treated at each step

25      Positions
25      Scores
25      Transferable

SNPLift: Percentage of transferred SNPs:

100.000%

SNPLift: Run completed

End: 20241111_112644

real    1m46.972s
user    0m30.731s
sys     0m46.692s
```
