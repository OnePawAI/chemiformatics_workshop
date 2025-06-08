
# Rutgers Cheminformatics Workshop

This repository contains a collection of cheminformatics projects completed as part of the Rutgers Cheminformatics Crash Course. The notebooks cover SMILES parsing, molecular descriptor calculation, QSAR modeling, and protein–ligand interaction analysis.

## 📚 Notebooks

- `01_Cheminfo_crash_course.ipynb`  
  - SMILES parsing and visualization
  - Fingerprints and similarity analysis
  - Substructure search

- `02_Cheminfo_crash_course.ipynb`  
  - Molecular descriptor calculation using RDKit
  - Feature correlation analysis

- `03_Cheminfo_crash_course.ipynb`  
  - QSAR modeling (Random Forest Regression)
  - Model evaluation (R², MAE, plots)

- `04_Cheminfo_crash_course.ipynb`  
  - Protein–ligand interaction visualization
  - Pocket analysis using PDB structures

## Environment setup

To create the environment:

```bash
conda env create -f environment.yml
conda activate cheminfo_env
```

To register the environment with Jupyter (to make it appear in the Kernel list):

```bash
python -m ipykernel install --user --name=cheminfo_env --display-name "Python (cheminfo_env)"
```

To run the notebooks:

```bash
jupyter notebook
```

## How to Run Locally

To run this project locally, you first need to set up the environment as described in the [Environment setup](#environment-setup) section.

Then, follow these steps:

1. Clone this repo:

```bash
git clone https://github.com/OnePawAI/rutgers-cheminformatics.git
cd rutgers-cheminformatics
```

2. Install required packages (if using pip — not recommended for RDKit):

```bash
pip install -r requirements.txt
```

👉 Note: For RDKit-based workflows, using the provided `environment.yml` with conda is strongly recommended due to RDKit's C++ dependencies.

3. Run the notebooks:

```bash
jupyter notebook
```

## Notes on Scalability

This workshop was originally designed to run on small datasets (e.g., nsaids.csv) that fit well within Google Colab's free tier limits. For such small-scale cheminformatics tasks, Colab is sufficient.

However, real-world cheminformatics workflows often involve large datasets (millions of molecules), large descriptor matrices, and more intensive machine learning tasks (e.g., cross-validation, hyperparameter tuning).

In such cases, Google Colab's free tier presents limitations:
- Limited RAM (~12 GB)
- Session timeouts (up to 12 hours)
- Slow file I/O for large molecule datasets
- Unreliable GPU access

To address these limitations, this project also provides an `environment.yml` file to set up a local conda environment. Running these notebooks locally (e.g., on an Apple M3 Mac) allows for:
- Larger memory capacity
- No session timeouts
- Faster disk I/O for big datasets
- More reliable and cost-free execution for descriptor-based ML models

While this project focuses on traditional cheminformatics ML (Random Forest, QSAR), deep learning approaches (e.g., GNNs) may still require dedicated GPU hardware.

By running locally, this project can scale to larger datasets beyond what is practical in Colab free tier.

## Requirements

See `requirements.txt` and `environment.yml` for the full package list.

## License

MIT License.
