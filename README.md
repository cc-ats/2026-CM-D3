# 2026-CM-D3

This repository contains system setup files, simulation input files, free-energy data, and analysis scripts associated with the manuscript:
**“The Effect of Dispersion Corrections to Density Functionals on the Predicted Free Energy Profile of Chorismate Mutase Catalysis"**
by, 
Samitha Ranasinghe¹, Richard Van¹, Alberto dos Santos¹, Gabriel Deleon², Yuezhi Mao², and Yihan Shao¹

¹ Department of Chemistry, Brandeis University, Waltham, MA 02453, USA
² Department of Chemistry and Biochemistry, San Diego State University, San Diego, CA 92182, USA

The repository provides the files used to perform the QM/MM simulations and reproduce the free-energy and energy-reweighting analyses reported in the manuscript.

## Repository structure

### `system_setup/`

Files used to construct and describe the chorismate mutase simulation system.

Contents include:

- `2cht_amber.pdb` — starting protein structure
- `CHO.mol2` — chorismate structure and atom parameters
- `CHO.frcmod` — additional force-field parameters for chorismate
- `step3_pbcsetup.parm7` — AMBER topology file for the solvated system
- `step3_pbcsetup.rst7` — AMBER coordinate/restart file for the solvated system
- `step3_pbcsetup.pdb` — PDB representation of the prepared system
- `tleap.in` — tleap input used for system preparation

### `input_files/`

Input files used for equilibration, production QM/MM simulations, and definition of the reaction coordinate.

Contents include:

- AMBER `.mdin` files used for equilibration and production calculations
- QMHub configuration files for calculations with and without the D3(BJ) dispersion correction
- `cv.rst` — collective-variable/restraint definition
- `prod.ncrst` — restart coordinates used for production calculations

### `freefile_mbar_files/`

Free-energy data used for MBAR analysis of the umbrella-sampling simulations.

The directory is divided into:

- `nod3/` — free-energy data obtained from B3LYP calculations without the D3(BJ) dispersion correction
- `withd3/` — free-energy data obtained from B3LYP-D3(BJ) calculations

Separate files are provided for each QM-region definition investigated in the manuscript, including the CHO-only QM region and QM regions containing individual active-site residues.

### `scripts/`

Jupyter notebooks and numerical data used for free-energy analysis and energy reweighting.

Contents include:

- `mbar.ipynb` — MBAR analysis used to construct the free-energy profiles
- `reweighting_energy.ipynb` — energy-reweighting analysis
- `D3andD4 energies.ipynb` — comparison of D3(BJ) and D4 energies
- `d3bj_energy.npy` and `d4_energy.npy` — D3(BJ) and D4 energy data used in the comparison
- `qmmm_6-31g*_D3BJM_energy_new.npy` — D3(BJ) QM/MM energies used for reweighting
- `qmmm_6-31g*_D4_energy_from_D3BJ_frames.npy` — D4 energies evaluated for configurations sampled from the D3(BJ) simulations

## Software

The simulations and analyses were performed using:

- AMBER
- QMHub
- Q-Chem
- Python
- PyMBAR
- Jupyter

## Data availability

The files in this repository contain the system setup, simulation inputs, free-energy data, and analysis scripts used to generate the principal free-energy and energy-reweighting results reported in the manuscript.

Molecular dynamics trajectory files are not included because of their large file size.
