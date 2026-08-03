# Cross-Cohort Harmonization & Model Transportability in Survival ML

An end-to-end machine learning pipeline investigating distribution shift, cross-population transportability, and within-cohort z-score harmonization using Random Survival Forests across distinct international research cohorts (emulating global consortia frameworks like COSMIC and DPAU).

---

## 📌 Project Overview

Predictive models trained on single-population cohorts often suffer performance degradation when applied to external populations due to demographic differences, varying baseline risk profiles, and site-specific measurement scales. This project evaluates:

1. **Simulated Global Cohorts:** Generating two distinct populations with structural demographic and clinical variance (Cohort A vs. Cohort B).
2. **Transportability Baseline:** Training a Random Survival Forest on Cohort A and testing model transportability on Cohort B.
3. **Cohort-Level Z-Score Harmonization:** Standardizing features independently within each cohort to align distributions while preserving relative risk rankings.
4. **Performance Benchmarking:** Quantifying performance recovery across raw vs. harmonized features using the Concordance Index (C-Index).

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.x
* **Environment:** Google Colab / Jupyter Notebook
* **Key Libraries:**
  * `pandas`, `numpy` – Cohort generation & data handling
  * `scikit-learn` – Feature standardization (`StandardScaler`)
  * `scikit-survival` – Non-linear Random Survival Forests (`RandomSurvivalForest`)
  * `matplotlib`, `seaborn` – Performance benchmarking plots

---

## 📊 Key Findings & Benchmarks

| Feature Strategy | Internal Validation (Cohort A C-Index) | External Transportability (Cohort B C-Index) | Key Takeaway |
| :--- | :---: | :---: | :--- |
| **Raw Unscaled Features** | **0.745** | **0.655** | Demonstrates clear covariate shift when applying raw model weights across cohorts. |
| **Z-Score Harmonized** | **0.745** | **0.670** | Harmonization improves external transportability (+0.015 C-Index) without degrading internal performance. |

---

## 🚀 How to Run

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Cohort_Harmonization_Survival_ML.git](https://github.com/YOUR_USERNAME/Cohort_Harmonization_Survival_ML.git)
   cd Cohort_Harmonization_Survival_ML
