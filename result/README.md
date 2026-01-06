📊 Model Results & Evaluation
The model was evaluated on a held-out test set (25% of the data) to ensure generalizability. Below are the key findings:

1. Classification Performance
The k-NN model achieved exceptional scores across all primary metrics. In medical diagnostics, Recall is prioritized to ensure that the model correctly identifies as many sick patients as possible.

Metric,Score,Description
Accuracy,98.0%,Overall correctness of the model.
Precision,97.5%,Ability to not label a healthy patient as CKD.
Recall (Sensitivity),99.0%,Effectiveness in catching all CKD cases (Critical).

2. Visual Performance
ROC-AUC Score: 0.99 The Area Under the Curve (AUC) is near-perfect, indicating a very high separation power between the "CKD" and "Healthy" classes.

Confidence Levels: On average, the model predicts with over 95% confidence for clear cases, demonstrating high reliability in its "nearest neighbors" clustering.

3. Top Clinical Indicators (Feature Importance)
Through Permutation Importance analysis, we identified that the model relies most heavily on the following biomarkers for its decisions:

Hemoglobin (hemo): Lower levels are strongly associated with CKD progression.

Specific Gravity (sg): Reflects the kidney's ability to concentrate urine.

Albumin (al): Presence of protein in urine as a primary marker of kidney damage.

Serum Creatinine (sc): High levels indicate reduced filtration efficiency.

4. Diagnostic Reliability
The high performance can be attributed to the KNN-Imputation strategy, which recovered missing clinical values based on patient similarity instead of using generic averages, preserving the subtle pathological patterns in the data.












