Microbiome analysis of 16S V3 amplicon data from Flurex
================

## Intro

This project covers 16S V3 amplicon sequencing data from fecal, cecal
and ileal samples collected during the project “Flurex” (internal animal
study no. R20-22). Study was conducted at the National Food institute at
Technical University of Denmark in the research group for Gut, Microbes
and Health. Code for the microbiome data analysis is publically
available with the publication of this study.

The project data contains 16S V3 amplicon sequencing from feces samples
from 4 different days and cecum and ileum samples from one day from 48
rats. There are feces samples from all rats from day 0, 2, 4 and 8.
Cecum and ileum samples were all collected at dissection on day 8.
Please read the method section for this paper for details on
experimental setup.

Metadata contains sample information regarding: - rat number/name, cage
number (rats were co-caged 2-2), day of sampling, material (feces,
cecum, ileum), sequencing information (gram of material used for
extracted DNA, DNA concentrations, primers, barcodes for demultiplexing,
batch number (“run” = c2, c3, c4)), treatment groups. Several columns
have been created for easy sample grouping during analysis, including
for distinguishing between vancomycin and PFOS treatment alone.

Metadata contains results from:

- Bodyweight per sampling day, while cecum and liver weight for day 8
  (addition column with organ weights normalised to bodyweight).

- PFOS quantification of:

  - Blood serum from day 4 and 8 measured in µg/mL
  - Liver tissue from day 8 measured in mg PFOS in full liver weight

- Short-chain fatty acids quantification of 10 compounds in colonic
  water given in mM from day 8:

  - formic acid (formate),
  - acetic acid (acetate),
  - propanoic acid (propionate),
  - 2-methyl-propanoic acid (isobutyrate),
  - butanoic acid (butyrate),
  - 3-methyl-butanoic acid (isovalerate),
  - pentanoic acid (valerate),
  - 4-methyl-pentanoic acid (isocaproate),
  - hexanoic acid (coproate) and
  - heptanoic acid (enanthate).

## Content

Analysis covers Import and QC of sequencing data in phyloseq objects
obtained from the
[DF_GMH_PIPELINE](https://github.com/MSMortensen/DF_GMH_pipeline), as
well as relative abundance, alpha-diversity, beta-diversity and
differential abundance analyses.

## How to use

Analyses should be run in the order given by the numbering of the
Rmarkdown documents: 1. 01_Import_QC.Rmd (Must be completed before
running any other analyses) 2. 02_AlphaDiversity.Rmd (Alpha diversity
calculations) 3. 03_BetaDiversity.Rmd (Beta diversity calculations) 4.
04_Differential_abundance.Rmd (Differential abundance calculations) 5.
05_Microbiome_description_feces.Rmd (Overview of relative abundances) 6.
06_Animal_data.Rmd
