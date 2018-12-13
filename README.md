# Bioinformatics Pipeline Building meeting - Demo 2018-12-13 on reproducibility using Snakemake and Conda

This code is provided to the participants of the Bioinformatics Pipeline Building meeting given on 2018-12-13 about how to achieve reproducibility in bioinformatics using Snakemake and Conda environments.

The final/ folder contains the finished version for each example, 
the demo/ folder contains the startup code for each example (usually the final code for the previous example).

## Missing data files

The fastq.gz files used during the demo are not here (can't be shared), you need 2 pairs of any Illumina paired-end fastq.gz files under the 
data folder to properly run the demo:  
`data/s1_r1.fastq.gz`   (sample 1, forward reads)  
`data/s1_r2.fastq.gz`   (sample 1, reverse reads)  
`data/s2_r1.fastq.gz`   (sample 2, forward reads)  
`data/s2_r2.fastq.gz`   (sample 2, reverse reads)  

## To execute the examples

Execute from the root directory of this git repository.  Note: you should delete the generated files in between examples, 
if Snakemake sees a file already exists, it usually assumes that the rule generating this file doesn't need to be run again.


### 1. Hello World

(first `cd final`, we demonstrate here that Snakemake will search for a file called `Snakefile` within the current directory and execute it if no other Snakefile is specified with the `-s` parameter)  
command: `snakemake`


### 2. Hello World 2

command: `snakemake -s final/01-Snakemake.slightly.longer`


### 3. A more realistic example with Trimmomatic

command: `snakemake -s final/02-Snakefile.just.Trimmomatic`


### 4. Chaining Trimmomatic and metaSPAdes

command: `snakemake -s final/03-Snakefile.Trimmomatic.and.metaSPAdes`


### 5. Using the Snakemake workdir: directive

command: `snakemake -s final/04-Snakefile.Trimmomatic.and.metaSPAdes.workdir`


### 6. About wildcards

command: `snakemake -s final/05-Snakefile.wildcards`


### 7. Using the --config command line parameter

command: `snakemake -s final/06-Snakefile.Trimmomatic.and.metaSPAdes.config --config manifest=final/manifest.tsv`


### 8. Using the --configfile command line parameter

command: `snakemake -s final/07-Snakefile.Trimmomatic.and.metaSPAdes.configfile --config manifest=final/manifest.tsv --configfile final/config.yaml`


### 9. Using a Python function() as an input

command: `snakemake -s final/08-Snakefile.Trimmomatic.and.metaSPAdes.fnt.as.input snakemake --config manifest=final/manifest.tsv --configfile final/config.yaml`


### 10. Using a conda environment

command: `snakemake -s final/09-Snakefile.Trimmomatic.and.metaSPAdes.conda.env snakemake --config manifest=final/manifest.tsv --configfile final/config.yaml --use-conda --conda-prefix ~/conda_envs`


