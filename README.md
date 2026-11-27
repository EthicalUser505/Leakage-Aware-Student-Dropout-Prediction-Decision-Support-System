# Leakage-Aware Student Dropout Prediction & Decision Support System

> **IEEE SCOReD 2026 (Multimedia University)** · *Temporal Feature Auditing · Leakage-Safe ML · Human-Centred Power BI*

Many universities identify academic struggles and dropout risk too late for meaningful intervention. Traditional Student Information Systems (SIS) function largely as passive record-keeping archives rather than proactive decision-support tools—missing opportunities to help students before withdrawal occurs.

This repository presents a **leakage-aware machine learning pipeline and six-page Power BI decision-support prototype** designed to turn academic, engagement, and psychosocial signals into timely, human-in-the-loop insights for **students** (personalized support), **advisors & educators** (early, non-punitive outreach), and **university administrators** (cohort trends, equity checks, and resource planning).

---

### ✨ Highlights at a Glance
- **Strict Leakage Control:** Excluding four un-timestamped/post-event proxies (`credits_completed`, `subject_failure_count`, `counseling_sessions_attended`, `attendance_rate`) before splitting reduced holdout AUC-ROC by **13.9 percentage points** (`0.9989` → **`0.8599`**)—exposing how easily leakage inflates early-warning scores.
- **Leakage-Safe Pipeline (`5,000` records):** 80/20 stratified split with preprocessing and SMOTE isolated strictly inside 5-fold cross-validation, where **XGBoost** led across metrics (**`0.8780` CV AUC-ROC**, **`59.51%` CV F1** at `0.50`).
- **Advisor-Aware Thresholding (`0.35` cutoff):** Catches **`70.0%` of holdout dropouts** (`170 / 243`) while flagging `34.6%` of the cohort (`346` alerts, `49.1%` precision)—highlighting real advising workload and the need for supportive outreach.
- **Six-Page Power BI Prototype:** Translates model probabilities, subgroup profiles, gain-based feature importance, and student-level records into an interactive review interface.

---

### 📂 Dataset Provenance & Reproducibility
The original dataset (`https://www.kaggle.com/datasets/zyan1999/student-dropoutdataset`), which was later removed by the original uploader, is included in this repository so the pipeline and experiments remain reproducible. *(Note: Because public records lack institutional timestamps and provenance metadata, findings serve as a methodological demonstration rather than a causal or production-ready institutional deployment.)*
