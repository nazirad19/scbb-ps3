# scbb-ps3
# Single-Cell RNA-seq Processing Pipeline using kallisto and bustools

This repository contains the workflow used to process single-cell RNA-seq data from raw FASTQ files to a gene count matrix and downstream analysis using scvi-tools. In this project, we used [kallisto](https://pachterlab.github.io/kallisto/) (with its BUS mode) and [bustools](https://bustools.github.io/) to generate a cell-by-gene count matrix from raw reads. The count matrix was then imported into Scanpy/AnnData and further analyzed using scvi-tools.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Requirements](#requirements)
- [Installation](#installation)
- [Processing Pipeline](#processing-pipeline)
  - [1. Build kallisto Index](#1-build-kallisto-index)
  - [2. Pseudoalignment with kallisto BUS](#2-pseudoalignment-with-kallisto-bus)
  - [3. Post-Processing with bustools](#3-post-processing-with-bustools)
- [Downstream Analysis](#downstream-analysis)
  - [Converting to AnnData and Quality Control](#converting-to-anndata-and-quality-control)
  - [scvi-tools Analysis](#scvi-tools-analysis)
- [Results](#results)
- [License](#license)

## Overview

This project demonstrates how to process raw single-cell RNA-seq FASTQ files using kallisto and bustools to obtain a cell-by-gene matrix. After generating the count matrix, we convert it into an AnnData object for quality control and analysis in Python using Scanpy and scvi-tools.

## Dataset

For this I used paired-end FASTQ files from a single-cell RNA-seq experiment ( `SRR30105682_1.fastq.gz` and `SRR30105682_2.fastq.gz` from PRJNA1143044). 


## Installation

### Using Conda

Create a new environment and install dependencies:
```bash
conda create -n scvi_env python=3.10
conda activate scvi_env
conda install -c bioconda kallisto bustools
pip install scanpy scvi-tools anndata numpy pandas matplotlib scikit-learn
