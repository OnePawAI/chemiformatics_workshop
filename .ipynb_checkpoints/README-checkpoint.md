
# Rutgers Cheminformatics Workshop

This repository contains a collection of cheminformatics projects completed as part of the Rutgers Cheminformatics Crash Course. The notebooks cover SMILES parsing, molecular descriptor calculation, QSAR modeling, and protein–ligand interaction analysis.

## 📚 Notebooks

- `01_cheminfo_crash_course.ipynb`  
  - SMILES parsing and visualization
  - Fingerprints and similarity analysis
  - Substructure search

- `02_cheminfo_crash_course.ipynb`  
  - Molecular descriptor calculation using RDKit
  - Feature correlation analysis

- `03_cheminfo_crash_course.ipynb`  
  - QSAR modeling (Random Forest Regression)
  - Model evaluation (R², MAE, plots)

- `04_cheminfo_crash_course.ipynb`  
  - Protein–ligand interaction visualization
  - Pocket analysis using PDB structures

## Environment setup

To create the environment:

```bash
conda env create -f environment.yml
conda activate cheminfo_env


## How to Run Locally

1. Clone this repo:

```bash
git clone https://github.com/onepawai/rutgers-cheminformatics.git
cd cheminformatics-portfolio
```

2. Install required packages:

```bash
pip install -r requirements.txt
```

3. Run the notebooks:

```bash
jupyter notebook
```

## Requirements

See `requirements.txt` for the full package list.

## License

MIT License.

Toogle on /off in jupyter notebook
since pip install -r requirements is not suitable for rdkit (has c++ dependencies), equivalent environment.yml was created ""
