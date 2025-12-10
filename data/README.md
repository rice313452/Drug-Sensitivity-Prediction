# 📂 Dataset Information

Due to file size limitations, the original dataset files are **NOT included** in this repository.

Please download the **GDSC2 (Genomics of Drug Sensitivity in Cancer)** dataset from Kaggle or the official Sanger Institute website.

## ⬇️ Download Instructions

1. **Source:** [Kaggle: Genomics of Drug Sensitivity in Cancer (GDSC)](https://www.kaggle.com/datasets/sriharipramod/genomics-of-drug-sensitivity-in-cancer-gdsc)

2. **Required Files:**
   Download and place the following files into this `data/` directory:
   * `GDSC2-dataset.csv`
   * `Compounds-annotation.csv (already included)`
   * `Cell_Lines_Details.xlsx (already included)`

## 📁 Expected Directory Structure

After downloading, your project folder should look like this:

```text
DeepDrug-Sensitivity-Prediction/
├── data/
│   ├── README.md               <-- This file
│   ├── GDSC2-dataset.csv       <-- Place here
│   ├── Compounds-annotation.csv <-- Place here
│   └── Cell_Lines_Details.xlsx <-- Place here
├── src/
│   └── deep_drug_model.py
└── ...
