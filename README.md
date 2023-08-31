## Mapping-vs-Assembly Based SV Calling Evaluation

## Contributors :
1. Qian Zeng (Labcorp)
2. Ayan Malakar (Columbia University)
3. Qiyi Yu (Carnegie Mellon University)
4. Colin Diesh (University of California, Berkeley)
5. Seung Jae Lee (University of Southern California)
6. Carolina Jaramillo Oquendo (University of Southampton, U.K.)
7. Peiming (Peter) Huang (Baylor College of Medicine)
8. Sagayamary Sagayaradj (BASF)

## Introduction :
The goal of this project is to evaluate the performance of SV calling tools for NGS short-read dataset. Much of the current clinical testing is still short-read based, and with this project, we want to find an optimized SV calling protocol for analyzing large-scale short-reads dataset.

## Methods :
### Methods Overview :
SV calling methods generally fall into two groups:  mapping-based and assembly-based.   In mapping based methods, short reads are first aligned to a reference genome and SVs are then called based on the read alignment.  For the assembly based methods, reads can be assembled directly into contigs (“global assembly”), or reads could be aligned to a reference genome and then reads aligned to each region could be assembled into contigs (“local assembly”), and the contigs (and the corresponding reads) are then aligned to the reference genome for SV calling.
Once the SV calls are available, the performance of the SV calling protocol can be evaluated by comparison with an independently developed high-confidence truth set.  For this purpose, we are using the GIAB HG002 (ASJ son) SV dataset as the truth.  The findings will help us to assess the pros and cons for each method and recommend an optimized SV calling protocol for NGS short reads.

### Alignment based SV calling :
#### Step 1:
#### Step 2:
#### Step 3:
#### Step 4:
#### Step 5:

### Assembly based SV calling :
#### Step 1:
#### Step 2:
#### Step 3:
#### Step 4:
#### Step 5:

## Workflow :

![SV_hack_draft_2](https://github.com/collaborativebioinformatics/SVHack_assemblyvmapping/assets/22775490/2a59dc8b-cbb4-4966-8b22-75d019483526)

## Example Output :

```
## SV results:


```

## Results and Discussion :

