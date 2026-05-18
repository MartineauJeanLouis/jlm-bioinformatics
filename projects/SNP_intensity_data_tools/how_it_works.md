# ⚙️ How It Works — SNP-Array Processing Workflow

This document explains how the SNP-array processing workflow operates from raw Illumina IDAT files to analysis-ready outputs and CNV-compatible signal files.

The workflow was designed to provide:

- reproducibility
- scalability
- automated preprocessing
- transparent quality control
- high-throughput execution
- compatibility with downstream genomic analysis

---

# 🧬 Pipeline Overview

The workflow processes Illumina SNP-array datasets through multiple automated stages:

```text
Raw IDAT Files
        ↓
Data Preparation
        ↓
IAAP Genotype Calling
        ↓
GTC → TSV Conversion
        ↓
Intensity Feature Extraction
        ↓
Quality Control Analysis
        ↓
PFB Estimation
        ↓
Per-Sample Outputs
        ↓
Optional CNV Processing
````

Each stage is orchestrated using Snakemake, enabling reproducible and scalable execution.

---

# 📁 Step 1 — Input Data Preparation

The workflow begins with raw Illumina SNP-array files.

Typical inputs include:

* `.idat` files
* manifest files
* cluster definition files
* sample sheets

The pipeline automatically:

* validates input structure
* organizes datasets
* prepares directory layouts
* standardizes file handling

Optional functionality includes automated retrieval of public GEO datasets.

---

# 🔧 Step 2 — Environment & Toolchain Setup

The workflow automatically installs or configures required tools.

This includes:

* `htslib`
* `bcftools`
* `samtools`
* `gtc2vcf`
* IAAP integration

Reference genome preparation is also automated:

* FASTA download
* indexing
* genome preparation

This ensures reproducible execution across environments.

---

# 🧪 Step 3 — Genotype Calling

Raw IDAT intensity files are converted into GTC genotype files using IAAP.

This stage performs:

* genotype calling
* signal normalization
* array interpretation

The workflow supports:

* parallel execution
* multi-threaded processing
* scalable batch analysis

---

# 📊 Step 4 — Feature Extraction

Generated GTC files are converted into structured tabular outputs using `gtc2vcf`.

The workflow extracts key SNP-array metrics:

| Feature | Description                   |
| ------- | ----------------------------- |
| GT      | Genotype call                 |
| BAF     | B Allele Frequency            |
| LRR     | Log R Ratio                   |
| X/Y     | Normalized signal intensities |
| gcScore | Genotyping confidence metric  |

Outputs are standardized for downstream statistical and genomic analyses.

---

# 🧬 Step 5 — Quality Control Analysis

A dedicated QC module analyzes both probe-level and sample-level quality metrics.

## Probe-Level QC

Evaluates:

* probe call rate
* missingness
* signal consistency

## Sample-Level QC

Evaluates:

* genotyping success rate
* signal distribution
* intensity quality
* cohort consistency

The workflow identifies:

* low-quality samples
* problematic probes
* abnormal intensity patterns

---

# 📈 Step 6 — PFB Estimation

The workflow computes Population B Allele Frequency (PFB) values across probes.

PFB estimation is important for:

* CNV analysis
* population-level normalization
* downstream statistical interpretation

The pipeline includes handling for edge cases such as probes with missing genotype distributions.

---

# ⚡ Step 7 — GPU Acceleration (Optional)

Selected analytical components can optionally leverage GPU acceleration using CuPy.

Benefits include:

* faster matrix operations
* accelerated QC computation
* improved scalability for large cohorts

The workflow can run in:

* CPU-only environments
* GPU-enabled workstations
* HPC clusters
* cloud infrastructures

---

# 🧾 Step 8 — Output Generation

The pipeline generates structured and analysis-ready outputs.

## Main Outputs

### Per-Sample Files

Contains:

* SNP identifiers
* BAF values
* LRR values
* genotype calls
* intensity metrics

### QC Reports

Contains:

* sample QC metrics
* probe QC metrics
* summary statistics

### Visualization Outputs

Optional plotting includes:

* intensity distributions
* QC histograms
* density plots
* CNV visualization support

---

# 🔬 Step 9 — Optional CNV Integration

The workflow optionally integrates PennCNV for CNV analysis.

Generated outputs include:

* CNV-ready signal files
* PFB-compatible datasets
* GC-model compatible inputs
* automated CNV calling outputs

This enables scalable CNV preprocessing directly from raw SNP-array data.

---

# 🏗️ Why Snakemake?

Snakemake was selected because it provides:

* reproducible workflows
* modular architecture
* automatic dependency tracking
* scalable execution
* HPC compatibility
* cloud compatibility

Benefits include:

✅ restartable workflows
✅ efficient parallelization
✅ transparent execution
✅ reproducible environments

---

# 🚀 Scalability

The workflow was specifically designed for large-scale genomic studies.

Supported environments include:

* local workstations
* Linux servers
* HPC clusters
* cloud computing platforms

Scalability features include:

* multi-core processing
* parallel execution
* configurable resource allocation
* GPU acceleration support

---

# 🎯 Design Philosophy

The workflow was designed around several core principles:

## Reproducibility

Ensuring deterministic and version-controlled execution.

## Transparency

Providing clear QC reporting and interpretable outputs.

## Scalability

Supporting both small studies and large genomic cohorts.

## Modularity

Allowing adaptation to different datasets and analytical needs.

## Automation

Reducing manual intervention and analytical inconsistencies.

---

# 🔍 Typical Use Cases

This workflow is well suited for:

* SNP-array preprocessing
* genomic quality control
* population genetics
* CNV preprocessing
* clinical genomics
* large cohort studies
* downstream machine learning workflows


# 📫 Collaboration

For consulting inquiries or collaboration opportunities:

* custom QC procedures
* downstream analytical integration
* cloud/HPC deployment

The workflow can be customized for:

* non-standard datasets
* new array platforms

📧 **Professional Email**
[martineau.jeanlouis.bioinfo2017@gmail.com](mailto:martineau.jeanlouis.bioinfo2017@gmail.com)

🔵 **LinkedIn profile url**
www.linkedin.com/in/jean-louis-martineau-b329981b4


