## Mapping-vs-Assembly Based SV Calling Evaluation

## Contributors :
1. Qian Zeng (Labcorp)
2. Ayan Malakar (Columbia University)
3. Colin Diesh (University of California, Berkeley)
4. Peiming (Peter) Huang (Baylor College of Medicine)
5. Seung Jae Lee (University of Southern California)
6. Sagayamary Sagayaradj (BASF)

![logo](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/2bab3b86-3584-4cc6-9caa-d43e8320c2dd)

## Introduction :
The goal of this project is to evaluate the performance of SV calling tools for NGS short-read dataset. Much of the current clinical testing is still short-read based, and with this project, we want to find an optimized SV calling protocol for analyzing large-scale short-reads dataset.

## Methods :
### Methods Overview :
SV calling methods generally fall into two groups:  mapping-based and assembly-based.   In mapping based methods, short reads are first aligned to a reference genome and SVs are then called based on the read alignment.  For the assembly based methods, reads can be assembled directly into contigs (“global assembly”), or reads could be aligned to a reference genome and then reads aligned to each region could be assembled into contigs (“local assembly”), and the contigs (and the corresponding reads) are then aligned to the reference genome for SV calling.
Once the SV calls are available, the performance of the SV calling protocol can be evaluated by comparison with an independently developed high-confidence truth set.  For this purpose, we are using the GIAB HG002 (ASJ son) SV dataset as the truth.  The findings will help us to assess the pros and cons for each method and recommend an optimized SV calling protocol for NGS short reads.

### Alignment based SV calling :
We selected 2x250bp BAM files (80X coverage) from HG002 (Ashkenazim Trio Son, NA24385) as the input for mapping-based SV calling with Lumpy, Delly, Manta, Tardis, dysgu, cue and followed by Parliament (https://github.com/fritzsedlazeck/parliament2) and SURVIVOR (https://github.com/fritzsedlazeck/SURVIVOR).  The BAM files are converted to FASTQ files and used as input for assembly-based SV calling via SVABA, NucDiff and SVanalyzer, followed by SURVIVOR.  The individual SV calls and the consolidated SV calls are then compared with the HG002 SV truth dataset to assess the performance by Truvari.

### Assembly based SV calling :


## Workflow :

![SV_hack_draft_2](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/2a59dc8b-cbb4-4966-8b22-75d019483526)

## Example Output :

```
## SV results:


```

## Results and Discussion :

