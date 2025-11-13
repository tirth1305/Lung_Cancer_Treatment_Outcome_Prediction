# 🧠 Lung Cancer Treatment Outcome Prediction Using CatBoost

This project predicts **treatment outcomes** in lung adenocarcinoma patients using clinical and pathological features derived from **TCGA-LUAD** data.  
The goal is to leverage interpretable machine learning to assist precision oncology and outcome forecasting.

---

## 🚀 Objective
To build a multi-class classification model that predicts the **treatment outcome** of lung cancer patients based on demographic, diagnostic, and therapeutic data.

---

## 🧩 Dataset

- **Source:** TCGA-LUAD  
- **Target Column:** `treatments.treatment_outcome`  
- **Classes:**
  - Complete Response  
  - Partial Response  
  - Stable Disease  
  - Progressive Disease  

| Step | Description |
|------|--------------|
| Encoding | Converted categorical columns into category codes |
| Balancing | Used `RandomOverSampler` to achieve equal class distribution |
| Splitting | Stratified 80/20 train-test split |

---

## 🧠 Model: CatBoost Classifier

### Key Hyperparameters
| Parameter | Value |
|------------|--------|
| iterations | 2000 |
| learning_rate | 0.01 |
| depth | 4 |
| l2_leaf_reg | 10 |
| bootstrap_type | Bernoulli |
| subsample | 0.8 |
| loss_function | MultiClass |
| eval_metric | Accuracy |
| early_stopping_rounds | 150 |

---

## 🧮 Cross-Validation & Evaluation

**5-Fold Stratified Cross-Validation**

| Metric | Mean ± Std |
|:--------|:------------:|
| Accuracy | ~0.93 ± 0.02 |
| F1-Score | ~0.93 |

### **Final Model Performance**
| Metric | Train | Test |
|:-------:|:------:|:-----:|
| Accuracy | 0.9309 | 0.9275 |
| F1-Score | 0.9302 | 0.9268 |
| Accuracy Gap | 0.0034 | — |

➡️ The small accuracy gap indicates **excellent generalization**.

---

## 🔬 Top Predictive Features

| Rank | Feature | Importance |
|:----:|----------|:-----------:|
| 1 | demographic.age_at_index | 16.75 |
| 2 | diagnoses.ajcc_pathologic_stage | 15.17 |
| 3 | diagnoses.ajcc_pathologic_t | 14.37 |
| 4 | diagnoses.primary_diagnosis | 11.43 |
| 5 | diagnoses.ajcc_pathologic_m | 9.06 |
| 6 | diagnoses.ajcc_pathologic_n | 6.82 |
| 7 | diagnoses.icd_10_code | 6.41 |
| 8 | treatments.therapeutic_agents | 5.68 |
| 9 | diagnoses.tissue_or_organ_of_origin | 5.60 |
| 10 | diagnoses.residual_disease | 3.65 |

---

## 📊 Confusion Matrix
Shows strong predictive accuracy across all outcome classes with minimal misclassification.

---

## 🧰 Dependencies
pip install pandas numpy catboost scikit-learn imbalanced-learn matplotlib seaborn


## Research Context

This work demonstrates how machine learning can complement clinical oncology by identifying high-impact features influencing treatment outcomes in lung adenocarcinoma.

Dataset Source:
The Cancer Genome Atlas (TCGA-LUAD)

## 👨‍💻 Author

Tirth Patel
Department of Bioinformatics, Marwadi University
## 💡 Focus: Computational Genomics, Machine Learning, and Predictive Oncology
