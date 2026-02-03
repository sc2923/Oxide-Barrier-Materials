# First-Principles Defect Energetics Data for Oxide Barrier Materials

This repository contains the first-principles density functional theory (DFT) data used in the study:

**“Active-Learning Inspired *Ab Initio* Theory–Experiment Loop Approach for Management of Material Defects: Application to Superconducting Qubits”**

The data provided here support the defect-energetics descriptors used in the theory–experiment–machine-learning workflow presented in the manuscript.

---

## Contents of This Repository

This repository includes:

### 1. DFT Output Files
- Complete DFT output files for all calculations reported in the manuscript  
- Each directory corresponds to a specific material and defect configuration
- Output files include:
  - Total energies
  - Convergence information
  - Input parameters
  - Structural data

These files enable full reproducibility of the reported defect-formation-energy calculations.

---

### 2. Processed Defect Energetics Data
- Tabulated defect formation energies extracted from the raw DFT outputs
- CSV files used directly in the machine-learning analysis and descriptor maps
- Data formatted for ease of reuse and inspection

---

## Computational Details

All first-principles calculations were performed using the **JDFTx** software package:

> **JDFTx — Joint Density Functional Theory**
>  
> https://jdftx.org

JDFTx is an open-source plane-wave DFT code designed for high-performance electronic-structure calculations, including defect energetics and surface/interface systems.

Key computational parameters (exchange–correlation functional, k-point sampling, energy cutoffs, supercell sizes, etc.) are documented within the individual input and output files.

---

## Relation to Experimental Data

This repository contains **only the theoretical DFT data**.  
The corresponding **experimental characterization data (including XPS measurements)** are archived separately on Zenodo and are cited in the manuscript.

Together, the GitHub and Zenodo repositories provide the complete dataset supporting the findings of the study.

---

## Citation and Reuse

If you use data from this repository, please cite the associated manuscript and acknowledge the use of JDFTx.

This repository is intended to support transparency, reproducibility, and reuse of the defect-energetics data presented in the work.
