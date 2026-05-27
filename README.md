
# Pharmacokinetic Analysis of δ-Tocoflexol (DTF) vs δ-Tocotrienol (DT3) in Mice

## Overview

This repository contains the pharmacokinetic (PK) analysis from my PhD dissertation:

> **Rachael Oluwakamiye Abolade**  
> *Pharmacokinetics and Radiomitigation Efficacy of δ-Tocoflexol (DTF)*  
> University of Arkansas at Little Rock / University of Arkansas for Medical Sciences (UAMS), 2025

δ-Tocoflexol (DTF) is a novel vitamin E analog rationally designed to improve binding affinity for α-tocopherol transfer protein (ATTP), the hepatic protein responsible for recycling vitamin E into systemic circulation. By enhancing ATTP binding through increased tail flexibility, DTF achieves a significantly longer plasma half-life and greater systemic exposure than its parent compound δ-tocotrienol (DT3), positioning it as a pharmacokinetically optimized radiation medical countermeasure.

---

## Background

The vitamin E family comprises eight naturally occurring lipid-soluble antioxidants, four tocopherols and four tocotrienols. While tocotrienols exhibit superior radioprotective and radiomitigative biological activity compared to α-tocopherol (AT), their clinical utility is limited by short plasma half-lives (2 – 4.4 hours in humans) resulting from poor ATTP affinity.

DTF was computationally designed in the Compadre laboratory (UAMS) by replacing the tridienyl farnesyl tail of DT3 with a mono- or dienyl chain, increasing conformational flexibility and enabling DTF to adopt the bent conformation required for optimal ATTP binding, a conformation that DT3's rigid conjugated double-bond system cannot achieve.

---

## Study Design

- **Species:** Male C57BL/6J mice, 8–10 weeks of age
- **Dose:** 200 mg/kg subcutaneous injection
- **Compounds:** DTF and DT3 (vehicle: TOCOLFORM200)
- **Sample collection:** 0, 1, 2, 3, 6, 12, 24, 48, 96, and 192 hours post-administration
- **n = 40 mice** (groups A–F, n=6 each; group G, n=4 as baseline)
- **Analytical method:** GC/MS with internal standard (AT3) quantification
- **PK modeling:** Non-compartmental analysis (NCA) using Phoenix WinNonlin®

---

## Key PK Parameters

| Parameter | DT3 | DTF | Fold Difference |
|---|---|---|---|
| Cmax (µg/mL) | 13.0 | 49.0 | ~3.8× |
| Tmax (h) | 2 | 3 | — |
| AUClast (µg·h/mL) | 174.4 | 582.6 | ~3.3× |
| t½ est (h) | 6.5 | 24.5 | ~3.8× |

DTF achieved approximately **3.3× higher systemic exposure (AUC)** and **3.8× longer terminal half-life** compared to DT3 at the same dose. A secondary plasma concentration increase was observed for DTF between 96 – 192 hours, consistent with enterohepatic recirculation or delayed tissue redistribution, a feature not observed for DT3.

---

## Repository Structure

```
DTF_PK_Project/
├── README.md                   # This file
├── data/
│   ├── pk_raw_data.csv         # Raw plasma concentration data (µM) by time point
│   └── pk_parameters.csv       # Derived NCA PK parameters for DTF and DT3
├── scripts/
│   ├── pk_analysis.R           # Non-compartmental PK analysis in R
│   ├── pk_plots.R              # Concentration-time curve plots (log and linear)
│   └── pk_statistics.R         # Statistical comparison of PK parameters
├── results/
│   └── pk_summary_table.csv    # Summary table of all PK parameters
└── figures/
    ├── Figure1_log_pk_curve.png    # Log-scale concentration-time plot
    └── Figure2_linear_pk_curve.png # Linear-scale concentration-time plot
```

---

## How to Run

### Requirements

```r
install.packages(c("ggplot2", "dplyr", "tidyr", "readr", "PKNCA", "knitr"))
```

### Run the full analysis

```r
source("scripts/pk_analysis.R")
source("scripts/pk_plots.R")
source("scripts/pk_statistics.R")
```

---

## Key Findings

1. **Higher systemic exposure:** DTF's AUClast (582.6 µg·h/mL) was 3.3× greater than DT3 (174.4 µg·h/mL), indicating significantly improved bioavailability
2. **Extended half-life:** DTF's terminal half-life (24.5 h) was approximately 3.8× longer than DT3 (6.5 h), consistent with enhanced ATTP binding and slower hepatic clearance
3. **Higher peak concentration:** DTF achieved a Cmax of 49.0 µg/mL vs 13.0 µg/mL for DT3, exceeding the therapeutic threshold of 5 µM (approximately 2.5 µg/mL) by a wider margin
4. **Secondary plasma peak:** A secondary increase in DTF plasma concentration was observed at 192 hours, suggesting enterohepatic recirculation or delayed tissue redistribution, not observed for DT3
5. **Tocopherol-like kinetics:** DTF's PK profile (slow elimination, larger AUC, late recirculation) resembles that of α-tocopherol rather than tocotrienols, consistent with its improved ATTP binding design

---

## Clinical Relevance

These pharmacokinetic improvements directly underpin DTF's capacity to function as a **radiomitigator**,  an agent that must be administered *after* radiation exposure. DT3 is effective as a radioprotector only when given before or within 2–12 hours of exposure; DTF demonstrates radiomitigation efficacy at 24 hours post-exposure (70% 30-day survival vs 20% in vehicle controls at 8.5 Gy LD80), a window made possible by its extended systemic persistence.

---

## Citation

If you use this analysis, please cite:

> Abolade RO. *Pharmacokinetics and Radiomitigation Efficacy of δ-Tocoflexol*. PhD Dissertation, University of Arkansas at Little Rock / UAMS. 2025.

> Compadre CM, Singh A, Thakkar S, et al. Applications of Molecular Dynamics to the Design of Radioprotectant Tocotrienols with Enhanced Bioavailability. *Drug Dev Res.* 2014;75(1):10–22. doi:10.1002/ddr.21162

---


---

## Contact

**Rachael Oluwakamiye Abolade**  
Department of Information Science, Donaghey College of STEM  
University of Arkansas at Little Rock /   University of Arkansas for Medical Sciences
Little Rock, Arkansas
