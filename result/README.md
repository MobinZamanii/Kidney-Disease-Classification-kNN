# 📊 Model Results & Evaluation

The model was evaluated on a **held-out test set (25% of the data)** to ensure generalizability. Below are the key findings:

---

## Classification Performance

The **k-NN model** achieved outstanding results across all primary metrics. In medical diagnostics, **Recall (Sensitivity)** is prioritized to ensure that the model identifies as many CKD patients as possible.

| Metric    | Score  | Description                                                  |
|-----------|-------|--------------------------------------------------------------|
| ✅ Accuracy  | 98.0% | Overall correctness of the model                             |
| 🎯 Precision | 97.5% | Ability to avoid falsely labeling healthy patients as CKD   |
| 🩺 Recall (Sensitivity) | 99.0% | Effectiveness in detecting all CKD cases (Critical) |

---

## 📈 Visual Performance

- **ROC-AUC Score:** 0.99  
  The near-perfect AUC indicates strong separation between **CKD** and **Healthy** classes.

- **Confidence Levels:**  
  On average, the model predicts with **>95% confidence** for clear cases, demonstrating high reliability in its **nearest neighbors clustering**.

---

## 🔬 Top Clinical Indicators (Feature Importance)

Using **Permutation Importance**, the model relies most heavily on the following biomarkers:

| Feature | Clinical Insight |
|---------|-----------------|
| **Hemoglobin (hemo)** | Lower levels are strongly associated with CKD progression |
| **Specific Gravity (sg)** | Reflects the kidney's ability to concentrate urine |
| **Albumin (al)** | Presence of protein in urine, primary marker of kidney damage |
| **Serum Creatinine (sc)** | High levels indicate reduced filtration efficiency |

---

## 🧪 Diagnostic Reliability

The high performance is supported by the **KNN-Imputation strategy**, which recovers missing clinical values based on patient similarity rather than generic averages. This preserves subtle pathological patterns in the data, enhancing **diagnostic reliability**.

---

*This section summarizes the model's performance for documentation, reproducibility, and publication-ready reporting.*
