# Stroke Prediction — Machine Learning Project

## Dataset
**Source:** [Stroke Prediction Dataset — Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)

The dataset contains **5,110 patient records** with 12 clinical and lifestyle attributes used to predict whether a patient is likely to have a stroke.

---

## Project Description

This project builds an end-to-end binary classification pipeline to predict stroke occurrence using patient health data. It covers:

- **Exploratory Data Analysis (EDA)** — distribution plots, class imbalance analysis, correlation heatmaps
- **Data Preprocessing** — missing value imputation, label encoding, one-hot encoding, feature scaling
- **Class Imbalance Handling** — SMOTE (Synthetic Minority Over-sampling Technique)
- **Model Training** — Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost, KNN, SVM
- **Hyperparameter Tuning** — GridSearchCV with 5-fold Stratified Cross-Validation
- **Evaluation** — ROC-AUC, F1-Score, Confusion Matrix, Classification Report
- **Feature Importance** — Top 15 features from tuned XGBoost

### Best Model
| Metric | Score |
|--------|-------|
| Model | XGBoost (Tuned) |
| ROC-AUC | ~0.85+ |
| F1-Score | ~0.30+ (due to high class imbalance) |

### Key Predictors
1. `age`
2. `avg_glucose_level`
3. `bmi`
4. `hypertension`
5. `heart_disease`

---

## Project Structure

```
.
├── StrokePrediction_Project.ipynb   # Main Jupyter Notebook
├── healthcare-dataset-stroke-data.csv  # Dataset (download from Kaggle)
├── requirements.txt                 # Python dependencies
├── README.md                        # This file
├── StrokePrediction_ProjectReport.docx  # Full project report
├── stroke_xgb_model.pkl             # Saved trained model (generated on run)
├── stroke_scaler.pkl                # Saved feature scaler (generated on run)
└── *.png                            # EDA and evaluation plots (generated on run)
```

---

## Technologies Used

| Category | Library / Tool |
|----------|----------------|
| Language | Python 3.9+ |
| Data Manipulation | pandas, numpy |
| Visualisation | matplotlib, seaborn |
| Machine Learning | scikit-learn |
| Gradient Boosting | XGBoost |
| Imbalanced Data | imbalanced-learn (SMOTE) |
| Model Persistence | joblib |
| Notebook Environment | JupyterLab / Jupyter Notebook |

---

## Setup & Run Instructions

### 1. Clone / Download the project
```bash
git clone <your-repo-url>
cd stroke-prediction
```

### 2. Download the dataset
Download `healthcare-dataset-stroke-data.csv` from [Kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) and place it in the project root directory.

### 3. Create a virtual environment (recommended)
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

### 5. Launch Jupyter and run the notebook
```bash
jupyter notebook StrokePrediction_Project.ipynb
```
Run all cells in order (`Cell → Run All`).

---

## Output Files Generated
After running the notebook end-to-end, the following artefacts are created in the project directory:

| File | Description |
|------|-------------|
| `eda_overview.png` | Target distribution + age histogram |
| `eda_categorical.png` | Stroke rate by categorical features |
| `eda_numerical.png` | Numerical feature distributions |
| `correlation_heatmap.png` | Pearson correlation matrix |
| `roc_curves.png` | ROC curves for all models |
| `model_comparison.png` | AUC and F1 bar charts |
| `confusion_matrix.png` | Confusion matrix for tuned XGBoost |
| `feature_importance.png` | Top 15 feature importances |
| `stroke_xgb_model.pkl` | Serialised final model |
| `stroke_scaler.pkl` | Serialised feature scaler |

---

## License
This project is for educational purposes. The dataset is provided by [fedesoriano on Kaggle](https://www.kaggle.com/fedesoriano) under the [Open Database License](https://opendatacommons.org/licenses/odbl/).
