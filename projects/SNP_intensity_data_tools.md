````markdown id="f2k9mx"
# projects/SNP_intensity_data_tools.md

# 🔬 SNP_intensity_data_tools

## Overview

`SNP_intensity_data_tools` is a scalable and reproducible bioinformatics workflow developed for Illumina SNP-array preprocessing, intensity analysis, quality control, and CNV-ready signal generation.

The project transforms raw IDAT files into structured analysis-ready outputs suitable for downstream genomic analysis and CNV workflows.

---

# 🎯 Objectives

The workflow was designed to:

- automate SNP-array preprocessing
- standardize genomic signal extraction
- improve reproducibility
- provide transparent quality control
- support scalable execution
- enable downstream CNV analysis

---

# 🏗️ Workflow Architecture

```text
Raw IDAT Files
        ↓
IAAP Processing
        ↓
GTC Generation
        ↓
gtc2vcf Conversion
        ↓
TSV Extraction
        ↓
QC & Statistical Analysis
        ↓
PFB Estimation
        ↓
Per-Sample Outputs
        ↓
Optional PennCNV Integration
````

---


## Toolchain


* htslib
* bcftools
* samtools
* gtc2vcf

* IAAP
* PennCNV


---


## Workflow System


* Snakemake
* modular rule architecture
* configuration-driven execution

* parallelized processing


---

## Computational Features

* multi-threaded execution

* scalable cohort processing
* GPU-compatible QC workflows
* HPC deployment support

---


# 📊 Extracted Features

The pipeline generates:


| Feature | Description            |
| ------- | ---------------------- |
| GT      | Genotype call          |

| BAF     | B Allele Frequency     |
| LRR     | Log R Ratio            |
| X/Y     | Normalized intensities |
| gcScore | Genotyping confidence  |


---

# 🧪 Quality Control

The workflow computes:

## Probe-Level QC

* call rates
* missingness
* signal consistency

## Sample-Level QC

* genotyping success rate
* intensity quality
* cohort-level consistency

## Population Metrics

* PFB estimation
* signal normalization support

---

# 🧬 CNV Support

Optional PennCNV integration enables:

* CNV-ready signal generation
* automated signal preparation
* PFB compatibility
* scalable CNV preprocessing

---

# 🚀 Scalability

Designed for:

* local workstations
* Linux servers
* HPC clusters
* cloud infrastructure

Supports:

* multi-core execution
* parallel workflows
* GPU acceleration

---

# 📈 Outputs

Generated outputs include:

* structured per-sample TSV files
* QC summary tables
* PFB datasets
* visualization outputs
* CNV-compatible signal files

---

# 🔍 Applications

Suitable for:

* population genomics
* clinical genomics
* SNP-array preprocessing
* CNV workflows
* genomic QC systems
* downstream ML preprocessing

---

# 📫 Contact

For collaborations or workflow customization:

📧 [martineau.jeanlouis.bioinfo2017@gmail.com](mailto:martineau.jeanlouis.bioinfo2017@gmail.com)

```
```

