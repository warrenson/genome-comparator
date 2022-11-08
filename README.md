# genome-comparator
Compare Custom and Ensembl Genomes

## Input

### Custom Genomes
Fasta files of you favourite genome(s).

### Ensembl Genomes
Names (`ensembl_production_name`) of Ensembl Genomes.

## 01 Load Genomes with Annotations

### Custom Genomes
_Load_ each custom input genome into an Ensembl species DB and annotate it.

Use [Bio::EnsEMBL::Analysis::Hive::Config::Genome_annotation_conf](https://github.com/Ensembl/ensembl-analysis/blob/main/modules/Bio/EnsEMBL/Analysis/Hive/Config/Genome_annotation_conf.pm)

This is an Ensembl Hive Meta-Pipeline, wrapping many other Ensembl Analysis pipelines into one behemoth.

### Ensembl Genomes
Download from Ensembl FTP. Load genome with annotations for each Ensembl genome.

Use [Bio::EnsEMBL::Analysis::Hive::Config::LoadAssembly](https://github.com/Ensembl/ensembl-analysis/blob/main/modules/Bio/EnsEMBL/Analysis/Hive/Config/LoadAssembly.pm) perhaps.

## 02 Compare Genomes 
Compare custom genomes to Ensembl genomes using Ensembl Compara Hive pipeline.

Unsure which pipelines to attempt to use here, will investigate further.

https://github.com/Ensembl/ensembl-analysis/tree/main/modules/Bio/EnsEMBL/Analysis/Hive/Config

https://github.com/Ensembl/ensembl-compara/tree/release/108/modules/Bio/EnsEMBL/Compara/PipeConfig

## 03 Visualise
Build a docker compose cluster to run the Ensembl Web Browser for the comparison results.

Build an Ensembl Web browser (and all it's baggage) to attach to a DB server containing the species DBs. 
