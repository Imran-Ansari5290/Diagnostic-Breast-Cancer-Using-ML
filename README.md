# Diagnostic Breast Cancer Using ML

## Project Overview
**Diagnostic Breast Cancer Using ML** is a machine learning project based on the **Wisconsin Diagnostic Breast Cancer (WDBC)** dataset. The project performs data analysis, preprocessing, supervised classification, and unsupervised pattern analysis to classify observations as **malignant** or **benign**.

> **Note:** This is an educational machine-learning project and is not a clinical diagnostic system.

## Objectives
- Analyze the WDBC dataset.
- Perform data-quality checks and preprocessing.
- Prepare numerical features for machine learning.
- Build Logistic Regression and Random Forest classifiers.
- Evaluate models using multiple classification metrics.
- Apply stratified cross-validation.
- Use K-Means clustering to explore natural data groupings.
- Use PCA for lower-dimensional visualization.
- Interpret results, limitations, and possible improvements.

## Dataset
The project uses the **Wisconsin Diagnostic Breast Cancer (WDBC)** dataset available through Scikit-learn.

- **Samples:** 569
- **Input features:** 30 numerical features
- **Target:** Binary diagnosis
- **Classes:** Malignant and Benign

The features describe characteristics computed from digitized images of breast-cell nuclei, including measurements related to radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, and symmetry.

## Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

### Machine Learning Techniques
- Logistic Regression
- Random Forest
- K-Means Clustering
- Principal Component Analysis (PCA)
- Feature Selection
- Standardization
- Stratified Train/Test Split
- Stratified Cross-Validation

## Project Workflow
```text
Dataset Acquisition
        ↓
Data Inspection & Quality Checks
        ↓
Preprocessing
        ↓
Feature Selection / Scaling
        ↓
Supervised Learning
   ┌────┴────┐
   ↓         ↓
Logistic   Random
Regression Forest
   └────┬────┘
        ↓
Model Evaluation
        ↓
K-Means Clustering
        ↓
PCA Visualization
        ↓
Interpretation & Conclusions
```

## Data Preprocessing
The project includes:
1. Dataset inspection and descriptive analysis.
2. Missing-value and data-quality checks.
3. Separation of features and target.
4. Stratified train/test splitting.
5. Feature standardization where required.
6. Feature selection for Logistic Regression.
7. Pipeline-based preprocessing to reduce data leakage.

### Logistic Regression Pipeline
```text
Median Imputation
      ↓
StandardScaler
      ↓
SelectKBest
      ↓
Logistic Regression
```

The Logistic Regression workflow uses **SelectKBest with ANOVA F-test** and selects **20 features**.

## Machine Learning Models

### Logistic Regression
A linear classification model is used for binary diagnosis prediction.

Key configuration:
- `max_iter = 5000`
- `StandardScaler`
- `SelectKBest`
- `k = 20`

### Random Forest
A tree-based ensemble classifier is used for comparison.

Key configuration:
- `n_estimators = 300`
- `random_state = 42`
- `class_weight = "balanced"`
- `min_samples_leaf = 2`
- `n_jobs = -1`

## Model Evaluation
The project evaluates models using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix
- ROC Curve
- Stratified 5-Fold Cross-Validation

Multiple metrics are used because accuracy alone does not describe all types of classification errors.

## Unsupervised Learning

### K-Means Clustering
K-Means is applied to standardized feature data to explore whether observations naturally form groups.

Candidate values of **k = 2 to 6** are examined, with the **silhouette score** used to support cluster selection.

### PCA
Principal Component Analysis is used for dimensionality reduction and visualization of the high-dimensional feature space. PCA is primarily used for visualization rather than replacing the original classification features.

## Outputs
The notebook produces analysis and evaluation outputs such as:
- Dataset information
- Missing-value checks
- Descriptive statistics
- Feature analysis
- Classification metrics
- Confusion matrices
- ROC curves
- Cross-validation results
- K-Means analysis
- Silhouette analysis
- PCA visualization
- Final interpretation

## Project Structure
```text
Breast-Cancer-Diagnosis-ML/
├── diagnostic-breast-cancer-using-ml.ipynb
├── README.md
└── outputs
    ├── test_predictions
    ├── supervised_test_metrics
    ├── kmeans_selection
    └── cluster_diagnosis_percent
```

## How to Run

### Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### Start Jupyter or Kaggle(do not install any dependencies)
```bash
jupyter or Kaggle notebook 
```

Open:
```text
diagnostic-breast-cancer-using-ml.ipynb
```

Then run the notebook cells from beginning to end.

## Limitations
- The project uses a benchmark dataset rather than independent clinical datasets.
- Performance on this dataset does not establish clinical effectiveness.
- External validation is not included.
- K-Means clusters are exploratory and are not medical diagnoses.
- PCA can omit information from the original feature space.
- Classification thresholds can change precision and recall.

## Future Improvements
- Validate on independent datasets.
- Perform advanced hyperparameter optimization.
- Add probability calibration and threshold analysis.
- Compare additional ensemble models.
- Add explainable AI methods such as SHAP.
- Analyze feature importance and model interpretability.
- Build an educational web-based prediction dashboard.

## Learning Outcomes
This project demonstrates practical skills in:
- Data preprocessing
- Exploratory data analysis
- Feature selection and scaling
- Supervised machine learning
- Unsupervised machine learning
- Cross-validation
- Classification evaluation
- Confusion matrix and ROC-AUC analysis
- K-Means clustering
- PCA
- Reproducible machine-learning workflows

## Author
**Imran Ansari**

## Disclaimer
This project is for **educational and machine-learning demonstration purposes**. Its predictions should not be used as a substitute for professional medical examination, diagnosis, or treatment.
