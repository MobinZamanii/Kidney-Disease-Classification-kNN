# Kidney-Disease-Classification-kNN
# 🏥 Chronic Kidney Disease (CKD) Diagnostic Engine

## 📌 Executive Summary
This project implements a robust machine learning pipeline to predict **Chronic Kidney Disease (CKD)** using 24 clinical features (e.g., Albumin, Hemoglobin, Specific Gravity). 

Unlike standard textbook examples, this project focuses on **real-world data engineering challenges**: handling corrupt ARFF formats, imputing missing clinical data using **k-Nearest Neighbors (KNN)** to preserve biological relationships, and building an automated inference engine for deployment.

**Key Achievement:** The model achieves **>98% Accuracy** with a focus on high **Recall**, ensuring that potential CKD cases are not missed (False Negatives minimized).

---

## ⚙️ Technical Highlights

### 1. Data Ingestion & Cleaning (Custom Parsers)
* **Challenge:** The raw UCI dataset contained corrupt formats, mixed encodings (bytes/strings), and inconsistent typos (e.g., `\tno`, ` yes`).
* **Solution:** Built a custom parser to bypass standard library errors, utilizing Regex for deep cleaning and standardizing 24 feature columns.

### 2. Advanced Imputation (KNN vs. Mean)
* **Methodology:** Instead of simple mean/median imputation (which distorts clinical variance), I implemented **KNNImputer**.
* **Logic:** Missing values are estimated based on the "nearest" patients in the n-dimensional feature space, preserving the underlying medical correlations.

### 3. Model Optimization (Distance-Based Learning)
* **Algorithm:** k-Nearest Neighbors (k-NN).
* **Scaling:** Applied **Min-Max Scaling** to normalize all features to $[0, 1]$, preventing features with larger magnitudes (e.g., Blood Pressure) from dominating the Euclidean distance calculation.
* **Tuning:** Used the **Elbow Method** to scientifically determine the optimal $k$ value ($k=5$) to balance bias and variance.

---

## 📂 Project Structure

The project is designed as a modular pipeline following standard data science lifecycles:

| Notebook | Description | Key Tech |
| :--- | :--- | :--- |
| **01_EDA_and_Cleaning** | Raw ARFF loading, byte decoding, and typo resolution. | `Pandas`, `Regex` |
| **02_Feature_Engineering** | Label Encoding, KNN Imputation, and Scaling. | `KNNImputer`, `MinMaxScaler` |
| **03_Model_Tuning_and_Training** | Cross-Validation and Hyperparameter tuning (Elbow Plot). | `GridSearch`, `Elbow Method` |
| **04_Final_Evaluation_and_Inference** | ROC-AUC analysis, Confusion Matrix, and Inference. | `Seaborn`, `Scikit-learn` |
| **05_Executive_Dashboard** | High-level summary and interactive prediction tool. | `Data Visualization` |

---

## 📊 Performance Metrics

* **Optimal K:** 5
* **Accuracy:** ~98%
* **ROC-AUC Score:** 0.99
* **Key Predictors:** According to Permutation Importance, the most critical features for diagnosis are:
    1.  Hemoglobin (hemo)
    2.  Specific Gravity (sg)
    3.  Albumin (al)
    4.  Red Blood Cell Count (rc)

---

## 🚀 Usage & Inference

### Prerequisites
To run this project, install the required dependencies:
```bash
pip install pandas numpy scikit-learn seaborn matplotlib scipy
```
## 👨‍💻 Author
Mobin Zamani Data Scientist & Machine Learning Engineer
