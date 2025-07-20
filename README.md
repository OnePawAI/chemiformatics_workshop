# Rutgers Cheminformatics Workshop (Jupyter Edition)

This repository is an adapted version of the original **Cheminformatics-Driven Molecular Docking Workshop**, organized by the **Institute for Quantitative Biomedicine (IQB)** in collaboration with the **Protein Data Bank (PDB)**.

Each notebook was written by experts in the cheminformatics and molecular modeling community:

- **Notebook 1**: *Paul Craig (RIT Professor)* and *Jessica Nash (Software Scientist)*
- **Notebook 2**: *Pat Walters*
- **Notebook 3**: *Levi Naden (Software Scientist, MolSSI)* — with contributions from *Jessica Nash* and *Pat Walters*
- **Notebook 4**: *Jessica Nash (MolSSI)* — with feedback from *Pat Walters* and *David Koes*

---

## 🛠️ About This Version

This version of the workshop has been adapted to run entirely on **local Jupyter Notebooks** rather than Google Colab. Key enhancements include:

- 📦 A single `environment.yml` file for reproducible Conda environment setup
- 🐳 Use of **Docker** for GNINA docking (Notebook 4), enabling cross-platform support
- ⚡ Faster execution by avoiding repeated dependency installation
- 🔄 Improved flexibility for use on personal machines or HPC systems

> This adaptation makes the workshop more scalable and user-friendly for cheminformatics practitioners working with larger datasets or integrating GNINA workflows locally.

---

## 🐳 Docker Installation (for GNINA)

> GNINA is used in Notebook 04 for protein–ligand docking/visualization. You must have Docker installed to use GNINA.

### ✅ Ubuntu / Debian

```bash
sudo apt update
sudo apt install -y ca-certificates curl gnupg lsb-release

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin

# (Optional) Run Docker without sudo:
sudo usermod -aG docker $USER
newgrp docker
````

### ✅ macOS (Apple M1/M2/M3 or Intel)

1. Download Docker Desktop: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Install and launch Docker Desktop
3. Ensure Docker daemon is running (check in the menu bar)

### ✅ Windows 10/11

1. Download Docker Desktop: [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Enable **WSL2 backend** (required for Linux containers)
3. Restart after installation
4. Launch Docker Desktop and ensure it's running

> After installing Docker, test with:

```bash
docker run hello-world
```

---

## ⚙️ How to Run Locally

### 1. Clone this repository

```bash
git clone https://github.com/OnePawAI/rutgers-cheminformatics.git
cd rutgers-cheminformatics
```

### 2. Set up the Conda environment

The provided `environment.yml` file contains all necessary dependencies.

```bash
conda env create -f environment.yml
conda activate cheminfo_env
```

### 3. Register the Conda environment in Jupyter

```bash
python -m ipykernel install --user --name=cheminfo_env --display-name "Python (cheminfo_env)"
```

Now the environment will show up in Jupyter as `"Python (cheminfo_env)"`.

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

> 👉 **Note:** For RDKit workflows, using Conda is strongly recommended due to RDKit’s C++ dependencies.

---

## 🚀 Notebooks Overview

* `01_Cheminfo_crash_course.ipynb`

  * SMILES parsing, visualization, substructure search
* `02_Cheminfo_crash_course.ipynb`

  * RDKit descriptors, correlation analysis
* `03_Cheminfo_crash_course.ipynb`

  * QSAR modeling with Random Forest
* `04_Cheminfo_crash_course.ipynb`

  * Protein–ligand docking and visualization (requires Docker + GNINA)

---

## ⚖️ Notes on Scalability

Google Colab is convenient for small-scale cheminformatics tasks, but local execution provides:

* More memory and no timeouts
* Faster file I/O
* More control for large datasets
* Compatibility with tools like Docker and GNINA

For deep learning (e.g., GNNs), GPU hardware is still recommended.

---

## 📜 License

MIT License

