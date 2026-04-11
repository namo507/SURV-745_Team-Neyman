# SURV-745 Team Neyman

## Overview

This repository contains the final project materials for SURV 745: a multi-stage area probability sample design for the Detroit Transportation Security Survey.

The submission-ready package is collected in [Final deliverables](Final%20deliverables/).

The design targets adult residents of Detroit, Michigan and uses:

- census tracts as primary sampling units (PSUs)
- block groups as secondary sampling units (SSUs)
- adults aged 18+ as the ultimate sampling elements

The project was built to satisfy three main design goals:

1. obtain approximately 1,000 completed interviews
2. achieve 250 completes in each of four age groups
3. maintain self-weighting within age groups while keeping interviewer workload approximately equal across sampled PSUs

## Main Deliverables

### Final report

- [REPORT_NEYMAN.pdf](REPORT_NEYMAN.pdf): main written report with the full design, formulas, sample selection, anticipated precision, weighting plan, variance estimation guidance, maps, and appendices
- [REPORT_NEYMANN.qmd](REPORT_NEYMANN.qmd): updated Quarto source used to generate the final report deliverable
- [REPORT_NEYMAN.tex](REPORT_NEYMAN.tex): LaTeX output for the report
- [SURV745_Team_Neyman.qmd](SURV745_Team_Neyman.qmd): earlier project draft kept in the repository for reference
- [Project.pdf](Project.pdf): compiled project submission artifact included in the repository

### Frame and sample documentation

- [FRAME1_NEYMAN.pdf](FRAME1_NEYMAN.pdf): tract-level frame document
- [FRAME1_NEYMANN.Rmd](FRAME1_NEYMANN.Rmd): updated R Markdown source for the tract frame deliverable
- [FRAME1_NEYMAN.tex](FRAME1_NEYMAN.tex): current LaTeX output for the tract frame listing
- [FRAME2_NEYMAN.pdf](FRAME2_NEYMAN.pdf): block-group-level frame document
- [FRAME2_NEYMANN.Rmd](FRAME2_NEYMANN.Rmd): updated R Markdown source for the block-group frame deliverable
- [FRAME2_NEYMAN.tex](FRAME2_NEYMAN.tex): current LaTeX output for the block group frame listing
- [SAMPLE_NEYMAN.pdf](SAMPLE_NEYMAN.pdf): selected sample listing with probabilities and person-level sampling rates
- [SAMPLE_NEYMANN.Rmd](SAMPLE_NEYMANN.Rmd): updated R Markdown source for the selected-sample deliverable
- [SAMPLE_NEYMAN.tex](SAMPLE_NEYMAN.tex): current LaTeX output for the sample listing

### Input data

- [Census Tract FIPS Code Detroit MI.csv](Census%20Tract%20FIPS%20Code%20Detroit%20MI.csv): Detroit tract identifier list used to define the city frame
- [Detroit MI.xlsx](Detroit%20MI.xlsx): tract- and block-group-level Census inputs used in the sample design calculations
- [Census Tract FIPS Code Detroit MI_Updated.csv](Census%20Tract%20FIPS%20Code%20Detroit%20MI_Updated.csv): updated Detroit tract identifier list used by the final report source
- [Detroit MI_Updated.xlsx](Detroit%20MI_Updated.xlsx): updated tract- and block-group-level Census input file used by the final report source

## Final Folder

- [Final deliverables](Final%20deliverables/): submission-ready folder containing the final PDFs, TeX files, renamed source files, and updated input data under the required `NEYMAN` naming

## Key Results

The final design documented in the Quarto report produces the following headline results:

- target population: civilian, non-institutionalized Detroit adults aged 18+
- frame size after cleaning: 266 census tracts and 614 block groups
- total Detroit population in the frame: 639,090 persons
- total adult population in the frame: 480,102 adults
- selected PSUs: 40 census tracts
- selected SSUs: 40 block groups, one within each sampled tract
- target completed interviews: 1,000 total
- domain targets: 250 completes in each age group: 18 to 34, 35 to 49, 50 to 64, and 65+

### Sampling and workload results

- the design uses systematic PPS sampling at both the tract and block group stages
- a composite measure of size (MOS) is used to support both PPS selection and domain allocation
- the person-level design is self-weighting within each age group
- the expected interviewer workload is designed to be approximately constant across the 40 sampled PSUs

### Equal-rate comparison

The report shows that a single equal sampling rate for all adults would not meet the domain targets well. Under that alternative design, the 35 to 49 age group would fall short of its required completes, while some other age groups would be oversampled.

### Anticipated precision

For the example outcome of public transportation as the main mode of travel:

- anticipated design effect: 1.48
- anticipated standard error at $p = 0.15$: 0.0137
- anticipated coefficient of variation at $p = 0.15$: 9.2%
- approximate 95% confidence interval at $p = 0.15$: 0.123 to 0.177
- effective sample size: about 676

These values are documented in the anticipated precision section of the main report.

## Structure of the Main Report

The best place to start is [REPORT_NEYMAN.pdf](REPORT_NEYMAN.pdf). It is organized into the following major parts:

1. Introduction and survey objective
2. Sample design goals and target population
3. Frame construction and cleaning
4. Composite MOS derivation
5. Frame descriptive statistics
6. Equal-sampling-rate comparison
7. Stage 1 and Stage 2 sample selection
8. Person selection rules within sampled areas
9. Anticipated precision
10. Weighting plan
11. Variance estimation plan
12. Maps and appendices

## Figures

The report figures are stored in [figures](figures/) and include:

- [figures/fig_detroit_map.pdf](figures/fig_detroit_map.pdf): map of Detroit census tracts and selected PSUs
- [figures/fig_sample_map.pdf](figures/fig_sample_map.pdf): selected tracts and selected block groups
- [figures/fig_mos_distribution.pdf](figures/fig_mos_distribution.pdf): distribution of the composite measure of size
- [figures/fig_inclusion_probs.pdf](figures/fig_inclusion_probs.pdf): tract inclusion probabilities under PPS sampling
- [figures/fig_age_distribution.pdf](figures/fig_age_distribution.pdf): age distribution comparison
- [figures/fig_equal_rate.pdf](figures/fig_equal_rate.pdf): equal-rate design comparison
- [figures/fig_precision.pdf](figures/fig_precision.pdf): anticipated precision curve
- [figures/fig_workload.pdf](figures/fig_workload.pdf): workload balance visualization

## File Guide

### If you want the full narrative explanation

Read [REPORT_NEYMAN.pdf](REPORT_NEYMAN.pdf).

### If you want the source code and formulas

Read [REPORT_NEYMANN.qmd](REPORT_NEYMANN.qmd).

### If you want the tract frame

Read [FRAME1_NEYMAN.pdf](FRAME1_NEYMAN.pdf).

### If you want the block group frame

Read [FRAME2_NEYMAN.pdf](FRAME2_NEYMAN.pdf).

### If you want the selected sample listing

Read [SAMPLE_NEYMAN.pdf](SAMPLE_NEYMAN.pdf).

## Reproducibility Notes

The updated report and support sources rely on R packages referenced in [REPORT_NEYMANN.qmd](REPORT_NEYMANN.qmd), including:

- tidyverse
- readxl
- sampling
- knitr
- kableExtra
- sf
- tigris
- ggplot2
- glue

To rebuild the final deliverables, render [REPORT_NEYMANN.qmd](REPORT_NEYMANN.qmd), [FRAME1_NEYMANN.Rmd](FRAME1_NEYMANN.Rmd), [FRAME2_NEYMANN.Rmd](FRAME2_NEYMANN.Rmd), and [SAMPLE_NEYMANN.Rmd](SAMPLE_NEYMANN.Rmd) in an R environment with those packages installed and access to the updated input files already stored in this repository.

## Authors

- Team Neyman
- Namit Shrivastava
- Nicholas Reign Lugu

## Recommended Starting Point

If you only open one folder, open [Final deliverables](Final%20deliverables/). If you only open one file, open [REPORT_NEYMAN.pdf](REPORT_NEYMAN.pdf). It provides the clearest summary of the project motivation, sampling design, results, and supporting appendices.