# CSE445 ML Project: Hepatitis C Virus (HCV) Prediction Using Machine Learning

## 📌 Project Overview

This project presents a comprehensive machine learning pipeline for classifying the stages of Hepatitis C Virus (HCV) based on clinical and laboratory data. The work addresses critical challenges like class imbalance, feature noise, and low model interpretability by using a stack ensemble framework enhanced with modern preprocessing and explainability tools.

## 📊 Dataset

- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/503/hepatitis+c+virus+hcv+for+egyptian+patients)
- **Samples:** 1,385 instances
- **Features:** 29 attributes, including liver enzyme levels (ALT, AST), viral RNA load, and blood metrics (WBC, RBC, Platelets)
- **Target:** Binary classification based on **Baseline Histological Staging**

## 🔄 Preprocessing Pipeline

1. **Data Cleaning:** Removed missing/duplicated records
2. **Normalization:** Min-Max Scaling applied
3. **Feature Selection:** Recursive Feature Elimination (RFE) with Random Forest
4. **Class Balancing:** Borderline SMOTE for oversampling minority class

## 🤖 Machine Learning Models

### Base Learners:
- **Random Forest**
- **XGBoost**
- **Support Vector Machine (RBF Kernel)**
- **K-Nearest Neighbors**
- **Decision Tree**

### Ensemble Model:
- **Stacked Ensemble:** XGBoost as meta-classifier over the outputs of the base learners (RF, SVM, KNN, XGB).

## 📈 Evaluation Metrics

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **Confusion Matrix**
- **ROC Curve (AUC = 0.81)**

### Best Results (Stacked Ensemble Model):
- **Accuracy:** 88.45%
- **Precision / Recall / F1:** 0.88 each

## 🧠 Model Interpretability

- **LIME (Local Interpretable Model-Agnostic Explanations)** was used to:
  - Provide local explanations for individual predictions
  - Increase model transparency and clinical trustworthiness

## 📁 Project Structure

```
CSE445-PROJECT/
├── data/                           # Preprocessed data files
├── egyptian_patients_dataset/      # Raw dataset
├── ploting_data/                   # Visual data outputs
├── .gitignore
├── data_plotting.ipynb             # Visualization & EDA
├── final_project.ipynb             # Final model and analysis notebook
├── final_report.pdf                # Final report in IEEE format
├── requirements.txt
├── LICENSE
└── README.md
```

## 📌 Key Highlights

- Ensemble model significantly outperformed all individual models
- Borderline-SMOTE improved recall of minority (advanced fibrosis) class
- RFE reduced dimensionality while retaining essential predictive power
- LIME increased trust in the ML model via transparent explanation

## 🔭 Future Work

- Augment dataset with real-world Electronic Health Record (EHR) data
- Explore deep learning models (e.g., LSTM for time-sequence prediction)
- Deploy as a web application for clinical decision support

## 🛠️ Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt
```

### Key Libraries:
- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scikit-learn`, `xgboost`, `imbalanced-learn`, `lime`

## 📬 Contact

**Contributors:**
- Md. Saikot Hossain Sojib — `saikot.sojib@northsouth.edu`
- Md. Tasin Hossain Toha — `tasin.toha@northsouth.edu`

**Faculty Supervisor:**
- Dr. Riasat Khan, Associate Professor, ECE Dept, North South University