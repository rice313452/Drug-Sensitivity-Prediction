# DeepDrug: Dual-Tower Neural Network for Drug Sensitivity Prediction

## 📌 Project Overview
This project applies **Deep Learning (Dual-Tower Architecture)** to predict the drug response ($IC_{50}$) of cancer cell lines using the **GDSC2 (Genomics of Drug Sensitivity in Cancer)** dataset.

Unlike traditional machine learning approaches that often suffer from data leakage (using AUC/Z-Score as features), this model strictly utilizes **pre-experiment features** (Drug ID, Cell ID, Target Pathway, Cancer Type, Tissue Descriptors) to ensure realistic clinical applicability.

## 🚀 Key Results
| Metric | Value | Note |
| :--- | :--- | :--- |
| **R2 Score** | **0.8288** | High interpretability of variance |
| **MSE** | **1.3116** | Low prediction error |
| **Pearson Corr** | **0.91** | Strong linear correlation |

## 🧠 Model Architecture
We propose a **Dual-Tower DNN** to capture the latent interactions between drugs and cancer cells:
- **Drug Tower**: Embeds `Drug_ID` and `Target_Pathway`.
- **Cell Tower**: Embeds `Cell_ID`, `Cancer_Type` (TCGA), and hierarchical `Tissue_Descriptors`.
- **Interaction Head**: Concatenates features and predicts $LN\_IC_{50}$ via MLP.
- **Optimization**: Uses **Early Stopping** to prevent overfitting.

## 📂 Dataset
- **Source**: GDSC2 Dataset (Sanger Institute)
- **Target Variable**: `LN_IC50` (Natural Log of IC50)
- **Input Features**:
    - **Drug**: ID, Pathway
    - **Cell**: ID, TCGA Label, Tissue Type 1 & 2
    - **Excluded Features**: AUC, Z-Score, RMSE (To prevent **Data Leakage**)

## 📊 Explainable AI (XAI) Insights
We integrated SHAP and Virtual Screening techniques to validate biological significance:
1.  **SHAP Analysis**: Confirmed that **Drug ID** is the dominant factor, followed by biological pathways.
2.  **Virtual Screening**: The model successfully identified broad-spectrum drugs (e.g., *Camptothecin*) vs. resistant-prone drugs via heatmap analysis.
3.  **Tissue Sensitivity**: Verified that the model learns distinct sensitivity profiles across different tissue types (e.g., Lung vs. Skin).

## 🛠️ Usage
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
