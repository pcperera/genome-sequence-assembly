# Steps used for Bruijn graph assembling the mutant_R1.fastq and mutant_R2.fastq

* I used the https://github.com/ablab/spades tool to perform Bruijn graph assembly. SPAdes - St. Petersburg genome assembler - is an assembly toolkit containing various assembly pipelines.
* I followed the steps in https://github.com/ablab/spades to install spades on my Ubuntu laptop.
* cd results
* spades.py --pe1-1 ../data/mutant_R1.fastq --pe1-2 ../data/mutant_R2.fastq -o spades_bruijn_assembly_output (this will create assembly output in the results/spades_bruijn_assembly_output directory).

# Steps used for N50 and assembly coverage summary statistics calculation

* I used https://github.com/ablab/spades tool to generate the summary statistics
* pip install quast
* quast.py spades_bruijn_assembly_output/contigs.fasta  -r ../data/wildtype.fna


# Files

| File                                  | Description                                                                              |
|---------------------------------------|------------------------------------------------------------------------------------------|
| data                                  | contains the original mutant_R1.fastq, mutant_R2.fastq and reference genome wildtype.fna |
| results/spades_bruijn_assembly_output | spades tool based bruijn assembly output                                                 |
| results/quast_results                 | quast tool based statistics                                                              |
| results/quast_results/report.txt      | quast tool summary report                                                                |