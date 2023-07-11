Data analysis for Flurex project
================

## Intro

This project covers general data analysis as well as 16S V3 amplicon sequencing data from fecal, cecal
and ileal samples collected during the project “Flurex” (internal animal
study no. R20-22). Study was conducted at the National Food institute at
Technical University of Denmark in the research group for Gut, Microbes
and Health. R-based scripts used for data analysis is publicly available
with the publication of this study. Final study title is:

**Antibiotic modulation of the gut microbiota does not affect oral uptake and accumulation of perfluorooctane sulfonic acid (PFOS) in rats**

The project data contains weight data from all animals, quantitative data of short-chain fatty acids measured in colonic luminal content and PFOS measurements in serum and liver samples, and 16S V3 amplicon sequencing from feces samples from four different days along with cecum and ileum samples from one day from 48
rats. There are feces samples from all rats from day 0, 2, 4 and 8.
Cecum and ileum samples were all collected at dissection on day 8.
Please read the method section for this paper for details on
experimental setup.

Four input files are used:
 - Weight and quantitative data: *animal_data.csv*
 - PFOS isomer analysis data: *pfos_isomer_data.csv*
 - Microbiome data as phyloseq element and metadata: *flurex_data_full.RData* + *metadata_flurex_full.csv* 

All data documents contains sample information regarding animals and sample
origin, including:

- rat number/name
- cage number (rats were co-caged 2-2)
- day of sampling
- material (feces, cecum, ileum)
- sequencing information (gram of material used for extracted DNA, DNA
  concentrations, primers, barcodes for demultiplexing, batch number for microbiome data
  (“run” = c2, c3, c4))
- treatment groups and several columns created for easy sample grouping
  during analysis, including for distinguishing between vancomycin and
  PFOS treatment alone.

Metadata of microbiome data (*metadata_flurex_full.csv*) and *animal_data_R.csv* contains results from:

- Weight data:

  - Body weight per sampling day + body weight gain in percentage.
  - Cecum and liver weight for day 8 (addition columns with organ
    weights normalised to body weight).

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
  - heptanoic acid (enanthate)

Metadata of isomer proportions stored in *pfos_isomer_data.csv* contains
results from:

- Quantified linear, branched and total PFOS with relevant groupings

## Content

Analysis covers Import and QC of sequencing data in phyloseq objects
obtained from the
[DF_GMH_PIPELINE](https://github.com/MSMortensen/DF_GMH_pipeline), as
well as relative abundance, alpha-diversity, beta-diversity and
differential abundance analyses. Demultiplexed sequence files from raw
Ion S5 sequencing data are available under [Bioproject number
950015](http://www.ncbi.nlm.nih.gov/bioproject/950015). These can be
further processed for phyloseq analysis using the
[DF_GMH_PIPELINE](https://github.com/MSMortensen/DF_GMH_pipeline).

## How to use

Analyses should be run in the order given by the numbering of the
Rmarkdown documents:

1.  *01_Import_QC.Rmd* (Must be completed before running any other
    analyses)

2.  *02_AlphaDiversity.Rmd* (Alpha diversity calculations)

3.  *03_BetaDiversity.Rmd* (Beta diversity calculations)

4.  *04_Differential_abundance.Rmd* (Differential abundance calculations)

5.  *05_Microbiome_description_feces.Rmd* (Overview of relative
    abundances)

6.  *06_Animal_data.Rmd* (Data analysis and figures for data not related
    to microbiome)
