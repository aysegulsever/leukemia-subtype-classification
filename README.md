# Leukemia Subtype Classification (ALL vs. AML)

Gene expression (microarray) based classification of acute lymphoblastic (ALL)
vs. acute myeloid (AML) leukemia. Term project, interim report stage:
exploratory data analysis (EDA) and literature review. No model training yet.

## Datasets

| Dataset | Source | Platform | Samples | Probes |
| --- | --- | --- | --- | --- |
| Golub et al. (1999) | Kaggle "Gene expression dataset (Golub)" / DLI Module 19 | Affymetrix Hu6800 | 72 (47 ALL, 25 AML) | 7,129 |
| GSE14062 | NCBI GEO | GPL570 (HG-U133 Plus 2.0) | 140 (106 ALL, 34 AML) | 54,675 |

Raw data is NOT stored in this repository (`data/` is in `.gitignore`).

## Setup

```bash
pip install -r requirements.txt
```

Random seed: `SEED = 42` (see `src/config.py`).

## Getting the data



cat >> README.md <<'EOF'
# Leukemia Subtype Classification (ALL vs. AML)

Gene expression (microarray) based classification of ALL vs. AML leukemia.
Term project, interim report stage: EDA and literature review. No model training yet.

## Datasets

- Golub et al. (1999): Kaggle "Gene expression dataset (Golub)" / DLI Module 19.
  Affymetrix Hu6800, 72 samples (47 ALL, 25 AML), 7,129 probes.
- GSE14062 (NCBI GEO): GPL570 (HG-U133 Plus 2.0), 140 samples (106 ALL, 34 AML), 54,675 probes.

Raw data is NOT stored in this repository (data/ is in .gitignore).

## Setup

    pip install -r requirements.txt

Random seed: SEED = 42 (see src/config.py).

## Getting the data

1. Golub: download data_set_ALL_AML_train.csv, data_set_ALL_AML_independent.csv
   and actual.csv from the Kaggle page above and put them in data/.
2. GSE14062: downloaded automatically by the notebook with GEOparse
   (cached in geo_cache/, ignored by git).

## Running

Open notebooks/01_load_and_validate.ipynb (Google Colab or Jupyter) and run the
cells from top to bottom: data loading, quality checks, log2 transform, gene
filtering, PCA, t-SNE/UMAP, differential expression (Mann-Whitney U + BH),
train/test batch check, GSE14062 EDA, cross-dataset comparison (753 common genes).

## GenAI usage

See reports/genai_log.md.
