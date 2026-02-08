# First-Principles Defect Energetics Data for Oxide Barrier Materials

This repository contains the first-principles density functional theory (DFT) data used in the study:

**“Active-Learning Inspired *Ab Initio* Theory–Experiment Loop Approach for Management of Material Defects: Application to Superconducting Qubits”**

The preprint is available at https://arxiv.org/abs/2510.02544. The data provided here support the defect-energetics descriptors used in the theory–experiment–machine-learning workflow presented in the manuscript.

All first-principles calculations were performed using the **JDFTx** software package (version 1.7.0):

> **JDFTx — Joint Density Functional Theory**
>  
> https://jdftx.org

JDFTx is an open-source plane-wave DFT code designed for high-performance electronic-structure calculations, including defect energetics and surface/interface systems.

Key computational parameters (exchange–correlation functional, k-point sampling, energy cutoffs, supercell sizes, etc.) are documented within the individual input and output files.

This repository contains **only the theoretical DFT data**.  
The corresponding **experimental characterization data (including XPS measurements)** are archived separately on Zenodo (https://zenodo.org/records/17665093) and a citation is provided in the manuscript.

Together, the GitHub and Zenodo repositories provide the complete dataset supporting the findings of the study.

---

## Contents of This Repository

This repository includes:

### 1. DFT Input and Output Files
- Complete DFT input and output files (`DFT_data` folder) for all calculations reported in the manuscript
- Separated into interstitial (`DFT_data/interstitials` folder) and vacancy (`DFT_data/vacancies` folder) calculations
  - interstitial calculation folders (`DFT_data/interstitials/Xx` folder where `Xx` is the element name of the host metal) contain the following files:
    - `Xx_ion.in`         - input file for the relaxation of the reference supercell for the bulk metal
    - `Xx_ion.out`        - output file for the relaxation of the reference supercell for the bulk metal
    - `Xx_oct.in`         - input file for the relaxation of the supercell of the metal with an octohedral oxygen interstitial
    - `Xx_oct.out`        - output file for the relaxation of the supercell of the metal with an octohedral oxygen interstitial
    - `Xx_tet.in`         - input file for the relaxation of the supercell of the metal with an tetrahedral oxygen interstitial
    - `Xx_tet.out`        - out file for the relaxation of the supercell of the metal with an tetrahedral oxygen interstitial
  - vacancy calculation folders (`DFT_data/vacancies/Xx` folder where `Xx` is the element name of the host metal) contain the following files:
    - `XxO_ion.in`        - input file for the relaxation of the reference supercell for the bulk metal oxide
    - `XxO_ion.out`       - output file for the relaxation of the reference supercell for the bulk metal oxide
    - `XxO_vac.in`        - input file for the relaxation of the supercell of the metal oxide with an oxygen vacancy
    - `XxO_vac.out`       - output file for the relaxation of the supercell of the metal oxide with an oxygen vacancy
- These files enable full reproducibility of the reported defect-formation-energy calculations, when used with the JDFTx software available at https://jdftx.org.

### 2. Processed Defect Energetics Data
- Tabulated defect formation energies `DFT_Data - input.csv` extracted from the raw DFT outputs
  - this CSV file is used directly in the machine-learning analysis and descriptor maps

---

## Jupyter Notebooks

This repository also includes two Jupyter notebooks that demonstrate analysis workflows. To get these to work, download them along with the `DFT_Data - Input.csv` cav file also in the repository, and run them cell by cell.

### `logistic_regression.ipynb`
- Required Dependencies
  - numpy
  - matplotlib
  - scikit-learn
  - colour
  - scipy
- Plots diffusion barrier energies
- Plots progression of DFT and experimental data acquisition
- Performs logistic regression model at each iteration of data acquisition
- Plots the formation energy as a third axis to demonstrate correlation

### `lattice_mismatch.ipynb`
- Required dependencies
  - mp-api
  - emmet-core
  - pymatgen
  - pandas
  - numpy
  - matplotlib
  - scikit-learn
  - tqdm
- To get this to work, you must import your Materials Project id (which can be obtained here: https://next-gen.materialsproject.org/api) into the first line of the second cell
- Imports metals from the Materials Project database and calculates the lattice mismatch percent from niobium
- Imports the most stable oxide for  each metal, and plots the oxide formation energy vs the lattice mismatch percent
- Plots these values for the metals along with their logistic predictions

---

## Citation and Reuse

If you use data from this repository, please cite the associated manuscript and acknowledge the use of JDFTx.

This repository is intended to support transparency, reproducibility, and reuse of the defect-energetics data presented in the work.
