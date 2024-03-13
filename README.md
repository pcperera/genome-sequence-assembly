# Steps used for OLC assembling the mutant_R1.fastq and mutant_R2.fastq

* Run olc-assembler.ipynb

# Steps use for assembly coverage calculation

* cd data
* bwa index wildtype.fna
* bwa mem ../data/wildtype.fna olc_assembled_sequences.fasta > alignment.sam
* cd results
* bwa mem ../data/wildtype.fna olc_assembled_sequences.fasta > alignment.sam
* samtools view -bS alignment.sam | samtools sort -o alignment.sorted.bam
* bedtools genomecov -ibam alignment.sorted.bam -g ../data/wildtype.fna > coverage.txt


# Files

| File                                  | Description                             |
|---------------------------------------|-----------------------------------------|
| olc-assembler.ipynb                   | OLC assembly generation notebook        |
| results/olc_assembled_sequences.fasta | OLC assembled genome                    |
| data/wildtype.fna.amb                 | Generated from "bwa index wildtype.fna" |
| data/wildtype.fna.ann                 | Generated from "bwa index wildtype.fna" |
| data/wildtype.fna.bwt                 | Generated from "bwa index wildtype.fna" |
| data/wildtype.fna.pac                 | Generated from "bwa index wildtype.fna" |
| data/wildtype.fna.sa                  | Generated from "bwa index wildtype.fna" |
| results/alignment.sam                 | Generated from samtools                 |
| results/alignment.sorted.bam          | Generated from samtools                 |
| results/coverage.txt                  | OLC assembly coverage output            |
