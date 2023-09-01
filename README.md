## Mapping-vs-Assembly Based SV Calling Evaluation

## Contributors :
1. Qian Zeng (Labcorp)
2. Ayan Malakar (Columbia University)
3. Colin Diesh (University of California, Berkeley)
4. Peiming (Peter) Huang (Baylor College of Medicine)
5. Seung Jae Lee (University of Southern California)
6. Sagayamary Sagayaradj (BASF)

![logo](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/2bab3b86-3584-4cc6-9caa-d43e8320c2dd)

## Background :
Structural variants (SVs) are widely present in human genomes, but accurate detection of SVs in NGS data has been challenging.  A number of SV calling tools have been developed in the past few years, but it remains unclear what an ideal SV-calling protocol should look like.  The goal of this project is to develop a generalized framework to evaluate the performance of SV calling tools for NGS short-read dataset and to formulate an optimized SV-calling protocol. Since much of the current clinical testing is still short-read based, our goal is to define a SV calling protocol for analyzing large-scale short-reads dataset.

## Data Source :
https://github.com/genome-in-a-bottle/giab_data_indexes/blob/master/AshkenazimTrio/alignment.index.AJtrio_Illumina_2x250bps_novoalign_GRCh37_GRCh38_NHGRI_06062016.HG002
https://github.com/genome-in-a-bottle/giab_data_indexes/blob/master/AshkenazimTrio/alignment.index.AJtrio_Illumina300X_wgs_novoalign_GRCh37_GRCh38_NHGRI_07282015.HG002
The source location of the NIST HG002 benchmark: https://ftp-trace.ncbi.nlm.nih.gov/ReferenceSamples/giab/release/AshkenazimTrio/HG002_NA24385_son/NIST_SV_v0.6/

## Methods :
### Methods Overview :
SV calling methods generally fall into two groups:  mapping-based and assembly-based.   In mapping based methods, short reads are first aligned to a reference genome and SVs are then called based on the read alignment.  For the assembly based methods, reads can be assembled directly into contigs (“global assembly”), or reads could be aligned to a reference genome and then reads aligned to each region could be assembled into contigs (“local assembly”), and the contigs (and the corresponding reads) are then aligned to the reference genome for SV calling.
Once the SV calls are available, the performance of the SV calling protocol can be evaluated by comparison with an independently developed high-confidence truth set.  For this purpose, we are using the GIAB HG002 (ASJ son) SV dataset as the truth.  The findings will help us to assess the pros and cons for each method and recommend an optimized SV calling protocol for NGS short reads.

### SV calling :
We selected 2x250bp BAM files (80X coverage) from HG002 (Ashkenazim Trio Son, NA24385) as the input for mapping-based SV calling with Lumpy, Delly, Manta, Tardis, dysgu, cue and followed by Parliament (https://github.com/fritzsedlazeck/parliament2) and SURVIVOR (https://github.com/fritzsedlazeck/SURVIVOR).  The BAM files are converted to FASTQ files and used as input for assembly-based SV calling via SVABA, NucDiff and SVanalyzer, followed by SURVIVOR.  The individual SV calls and the consolidated SV calls are then compared with the HG002 SV truth dataset to assess the performance by Truvari.

## Workflow :

![workflow](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/14750f46-41f1-4663-804c-3e2b1400e34b)

## Results :

![truvari_for_dysgu](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/50e8debe-0352-4464-873b-62fd82d267ce)

```
## Scripts implemented:

```

## Discussion :

