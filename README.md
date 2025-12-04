# Single_cell_mouse_rectal_tissue_analysis_with_pseudobulking
Practice notebook for single cell mouse rectal tissue analysis with psedobulking
# Single-cell RNA-seq of Mouse Rectal Tissue with Pseudobulk Aggregation

This repository contains a complete analysis notebook for a single-cell RNA-seq dataset derived from mouse rectal tissue. The workflow demonstrates how to go from raw single-cell counts to a sample-level pseudobulk representation and principal component analysis (PCA) using Python.

The focus of this notebook is to:
- Load and inspect a large single-cell dataset (~1.1 GB `.h5ad` file)
- Perform basic quality control and preprocessing with **Scanpy**
- Preserve raw counts for downstream analysis in **AnnData** layers
- Aggregate single-cell data into **pseudobulk** profiles per sample
- Visualise sample-level variance using **PCA** on pseudobulk data

---

## Dataset

- **Input format:** `.h5ad` (AnnData object) containing single-cell expression data  
- **Biological source:** Mouse rectal tissue (likely including epithelial, immune and stromal cell populations)  
- **Additional metadata:** Sample-level information (e.g. condition, species, tissue, genotype, infection status) loaded from a separate `.csv` file and merged into `adata.obs`.

> Note: The raw data files themselves are not stored in this repository. Paths in the notebook assume the `.h5ad` and metadata `.csv` are accessible via Google Drive.

---

## Basic Tools and Libraries

The analysis is implemented in Python using:

- [Scanpy](https://scanpy.readthedocs.io/) – single-cell RNA-seq preprocessing and visualisation  
- [AnnData](https://anndata.readthedocs.io/) – data structure to store expression matrix + metadata  
- [decoupler](https://saezlab.github.io/decoupler-py/) – pseudobulk aggregation and (extendable to) pathway/TF analysis  
- `pandas`, `numpy`, `matplotlib`, `seaborn` – data handling and plotting

---
