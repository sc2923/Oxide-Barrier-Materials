# First-Principles Defect Energetics Data for Oxide Barrier Materials

This repository contains the first-principles density functional theory (DFT) data used in the study:

**“Active-Learning Inspired *Ab Initio* Theory–Experiment Loop Approach for Management of Material Defects: Application to Superconducting Qubits”**

The preprint is available at https://arxiv.org/abs/2510.02544. The data provided here support the defect-energetics descriptors used in the theory–experiment–machine-learning workflow presented in the manuscript.

All first-principles calculations were performed using the **JDFTx** software package:

> **JDFTx — Joint Density Functional Theory**
>  
> https://jdftx.org

JDFTx is an open-source plane-wave DFT code designed for high-performance electronic-structure calculations, including defect energetics and surface/interface systems.

Key computational parameters (exchange–correlation functional, k-point sampling, energy cutoffs, supercell sizes, etc.) are documented within the individual input and output files.

This repository contains **only the theoretical DFT data**.  
The corresponding **experimental characterization data (including XPS measurements)** are archived separately on Zenodo (https://zenodo.org/records/17665093) and are cited in the manuscript.

Together, the GitHub and Zenodo repositories provide the complete dataset supporting the findings of the study.

---

## Contents of This Repository

This repository includes:

### 1. DFT Input and Output Files
- Complete DFT input and output files for all calculations reported in the manuscript
- Separated in interstitial and vacancy calculations
  - interstitial calculation folders have the following files:
    - `Xx_ion.in`         - input file for the relaxation of the supercell of the metal
    - `Xx_ion.out`        - output file for the relaxation of the supercell of the metal
    - `Xx_oct.in`         - input file for the relaxation of the supercell of the metal with an octohedral oxygen interstitial
    - `Xx_oct.out`        - output file for the relaxation of the supercell of the metal with an octohedral oxygen interstitial
    - `Xx_tet.in`         - input file for the relaxation of the supercell of the metal with an tetrahedral oxygen interstitial
    - `Xx_tet.out`        - out file for the relaxation of the supercell of the metal with an tetrahedral oxygen interstitial
  - vacancy calculation folders have the following files:
    - `XxO_ion.in`        - input file for the relaxation of the supercell of the metal oxide
    - `XxO_ion.out`       - output file for the relaxation of the supercell of the metal oxide
    - `XxO_vac.in`        - input file for the relaxation of the supercell of the metal oxide with an oxygen vacancy
    - `XxO_vac.out`       - output file for the relaxation of the supercell of the metal oxide with an oxygen vacancy
- These files enable full reproducibility of the reported defect-formation-energy calculations.

### 2. Processed Defect Energetics Data
- Tabulated defect formation energies extracted from the raw DFT outputs
- CSV files used directly in the machine-learning analysis and descriptor maps
- Data formatted for ease of reuse and inspection

---

## Jupyter Notebooks

This repository also includes two Jupyter notebooks that demonstrate analysis workflows:

### `logistic_regression.ipynb`
- Plots diffusion barrier energies
- Plots progression of DFT and experimental data acquisition
- Performs logistic regression model at each iteration of data acquisition
- Plots the formation energy as a third axis to demonstrate correlation

### `lattice_mismatch.ipynb`
- Imports metals from the Materials Project database and calculates the lattice mismatch percent from niobium
- Imports the most stable oxide for  each metal, and plots the oxide formation energy vs the lattice mismatch percent
- Plots these values for the metals along with their logistic predictions

---

## Citation and Reuse

If you use data from this repository, please cite the associated manuscript and acknowledge the use of JDFTx.

This repository is intended to support transparency, reproducibility, and reuse of the defect-energetics data presented in the work.
