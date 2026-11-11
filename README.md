# DSA 1101 Practical Assignments

This repository contains completed, executable notebooks for the retail sales
and crop-yield practical assignments. The supplied workbook contains synthetic
teaching data; results must not be interpreted as real customer or farm
observations.

## Group members

1. Maxwell Mbondo - 24/06667
2. Mark Kitema - 24/06543
3. Hamdi Mohamed - 24/08115
4. Feisal Noor - 24/07112

## Files

- `A2_Retail_Sales_Analytics.ipynb` — retail data audit, cleaning, summaries,
  visualizations and introductory model comparison.
- `A3_Crop_Yield_Project.ipynb` — crop-yield audit, exploratory analysis,
  statistical summaries, visualizations and model comparison.
- `DSA1101_Practical_Assignments_Datasets.xlsx` — source workbook used by both
  notebooks.
- `outputs/` — cleaned CSV files, quality logs, analysis tables, figures and
  written reports.

## Run the notebooks

Use Python 3 and install the required packages:

```powershell
python -m pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl
```

Open either notebook in Jupyter or Google Colab and run all cells from a clean
kernel. Keep the source workbook beside the notebooks. The notebooks use a
fixed random seed and write analysis outputs under `outputs/`.

The retail regression reconstructs revenue from its defining arithmetic inputs;
it is not a demand forecast. Crop-yield relationships are observational and
cannot establish causal effects or justify farm-input prescriptions.
