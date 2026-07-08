# PBMC 3k scRNA-seq Analysis (Scanpy)

End-to-end single-cell RNA-seq pipeline built from raw counts through cell-type annotation, using the classic 10x Genomics PBMC3k dataset (Zheng et al. 2017).

## Dataset

**3k PBMCs from a Healthy Donor** — 2,700 peripheral blood mononuclear cells (T cells, B cells, NK cells, monocytes) profiled on 10x Genomics' platform. Loaded directly via `sc.datasets.pbmc3k()`.

## Pipeline steps

1. Load raw counts
2. QC metric calculation (gene counts, UMI counts, % mitochondrial reads)
3. QC visualization (violin + scatter plots)
4. Filtering (min 200 genes/cell, max 2500 genes/cell, max 6% mitochondrial reads)
5. Normalization (total-count, target sum 1e4) + log1p transform
6. Highly variable gene (HVG) selection
7. Regress out unwanted variation + scale
8. PCA
9. Neighbors graph + Leiden clustering
10. UMAP visualization
11. Marker gene identification (Wilcoxon rank-sum test)
12. Cluster annotation using canonical PBMC marker genes

## How to run
Open the notebook and run cells top to bottom.

## Skills demonstrated

QC filtering rationale, normalization, dimensionality reduction (PCA), graph-based clustering (Leiden), UMAP visualization, differential expression testing, and biological interpretation via marker genes.
