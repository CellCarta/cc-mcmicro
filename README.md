[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) ![Build Status](https://github.com/labsyspharm/mcmicro/actions/workflows/ci.yml/badge.svg)

# MCMICRO: Multiple-choice microscopy pipeline

MCMICRO is an end-to-end processing pipeline for multiplexed whole slide imaging and tissue microarrays developed at the [HMS Laboratory of Systems Pharmacology](https://hits.harvard.edu/the-program/laboratory-of-systems-pharmacology/about/). It comprises stitching and registration, segmentation, and single-cell feature extraction. Each step of the pipeline is containerized to enable portable deployment across an array of compute environments.

The pipeline is described in [Nature Methods](https://www.nature.com/articles/s41592-021-01308-y). Please see [mcmicro.org](https://mcmicro.org/) for documentation, tutorials, benchmark datasets and more.

## Quick start at CellCarta

1. Go to the EC2 orchestrator of your choice, acceptance or production
2. Convert your data into the following directory structure:
- root directory: the `markers.csv`, `params.yml` file and `registration` directory.
- registration directory: `.tiff` file.
3. run using
  ```shell

  nextflow run CellCarta/cc-mcmicro -profile AWS -bucket-dir s3://hgx-seq-work-acceptance20201223104707692700000001/mcmicro --in s3://hgx-seq-input-acceptance20201223104845345800000002/Comet/Data/test-mcmicro/ --out s3://hgx-seq-results-acceptance20201223105151986000000001/Comet/test
  ```

   



## Funding

This work is supported by the following:

* NCI grants U54-CA22508U2C-CA233262 and U2C-CA233280
* *NIH grant 1U54CA225088: Systems Pharmacology of Therapeutic and Adverse Responses to Immune Checkpoint and Small Molecule Drugs* 
* Ludwig Center at Harvard Medical School and the Ludwig Cancer Research Foundation
* Denis Schapiro was supported by the University of Zurich BioEntrepreneur-Fellowship (BIOEF-17-001) and a Swiss National Science Foundation Early Postdoc Mobility fellowship (P2ZHP3_181475). He is currently a [Damon Runyon Quantitative Biology Fellow](https://www.damonrunyon.org/news/entries/5551/Damon%20Runyon%20Cancer%20Research%20Foundation%20awards%20new%20Quantitative%20Biology%20Fellowships)
* NCI grant [1U24CA274494-01](https://reporter.nih.gov/project-details/10525124): Multi-Consortia Coordinating Center (MC2 Center) for Cancer Biology: Building Interdisciplinary Scientific Communities, Coordinating Impactful Resource Sharing, and Advancing Cancer Research

[Contributors](https://mcmicro.org/community/)
