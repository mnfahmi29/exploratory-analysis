**⚠️⚠️Desclaimer: due to my new step in Github, I will post my code as soon as possible⚠️⚠️**
# 🧭 Clinical Exploratory Analysis Pipeline

**Variable Structure • Individual Heterogeneity • Longitudinal Patterns**

> A reproducible exploratory workflow for clinical and REDCap-derived datasets, designed to discover latent structure in variables and individuals, and to generate hypotheses for future confirmatory studies.

---

## 📌 Project Scope

This repository implements a **layered exploratory analysis framework** for clinical data.
The goal is **not** prediction or causal inference, but **transparent discovery of patterns**, heterogeneity, and trajectories using both model-based and algorithmic approaches.

All analyses are explicitly **exploratory** and **hypothesis-generating**.

---

## 🧱 Conceptual Architecture

### **Variable Structure**

Purpose: understand relationships among variables and reduce redundancy.

* **Principal Components Analysis (PCA)**
  Explores variance structure and correlation patterns among continuous variables.

* **Factor Analysis (FA)**
  Explores continuous latent dimensions underlying observed correlations.

> ⚠️ PCA and FA are *not* used to define patient subtypes.

---

### **Individual Structure**

Purpose: explore heterogeneity among individuals (patients).

* **Clustering Analysis (Baseline)**
  Algorithmic similarity-based grouping (e.g., k-means, hierarchical).
  Used as a non-model-based reference.

* **Latent Class Analysis (LCA)**
  Model-based probabilistic subtyping using categorical indicators.

* **Latent Profile Analysis (LPA)**
  Continuous-variable analogue of LCA for phenotype discovery.

* **Latent Transition Analysis (LTA)** *(Longitudinal extension)*
  Explores transitions between latent states across repeated visits.

* **Latent Class Growth Analysis (LCGA) / Growth Mixture Models (GMM)** *(Longitudinal extension)*
  Identifies subgroups following distinct longitudinal trajectories.

> This layer constitutes the **primary exploratory discovery** component.

---

### **Documentation & Reasoning**

Purpose: ensure transparency, reproducibility, and scientific safety.

* **Quarto reports (`.qmd`)** integrating code, results, and interpretation
* Explicit **exploratory labeling** throughout
* Findings framed as **patterns and hypotheses**, not claims

---

## 🧪 Data Characteristics

* **Source:** REDCap-style clinical data
* **Structure:**

  * Cross-sectional and/or longitudinal
  * Supports repeated *instances* (e.g., multiple inpatient visits per patient)
* **Privacy:**

  * Only anonymized or synthetic data are included in the repository
  * No raw PHI is committed

---

## 📂 Repository Structure

```
clinical-exploratory-analysis/
├─ README.md
├─ R/
│  ├─ 01_import.R
│  ├─ 02_cleaning.R
│  ├─ 03_missingness.R
│  ├─ 04_variable_structure_PCA_FA.R
│  ├─ 05_individual_structure_clustering_LCA_LPA.R
│  ├─ 06_longitudinal_LTA_LCGA_GMM.R
│  └─ 99_utils.R
├─ reports/
│  └─ exploratory_report.qmd
├─ data/
│  └─ README.md        # data schema & expectations
├─ output/
│  ├─ figures/
│  └─ tables/
└─ docs/
   ├─ methods.md
   └─ interpretation_notes.md
```

---

## 🔄 Analysis Workflow

1. **Data Import & Cleaning**

   * Standardize variable names and types
   * Validate categorical vs continuous indicators

2. **Missingness Exploration**

   * Quantify missing data by variable, patient, and instance
   * Document strategy (complete-case vs imputation)

3. **Variable Structure (Layer 1)**

   * PCA: scree plots, loadings, variance explained
   * FA: factor loadings and latent dimensions

4. **Individual Structure (Layer 2)**

   * Clustering baseline
   * LCA / LPA model fitting and class interpretation
   * Uncertainty reporting (posterior probabilities, entropy)

5. **Longitudinal Extensions (Optional)**

   * LTA for latent state transitions
   * LCGA / GMM for trajectory-based subgroups

6. **Reporting & Interpretation (Layer 3)**

   * Quarto-based exploratory report
   * Clear limitations and next-step hypotheses

---

## ⚠️ Important Notes

* All results are **exploratory** and should not be interpreted as confirmatory evidence.
* P-values, if shown, are descriptive and hypothesis-generating.
* This repository is intended as:

  * a methodological template,
  * a teaching artifact,
  * and a foundation for future confirmatory studies.

---

## 🚀 Intended Use

This repository is suitable for:

* Clinical exploratory data analysis
* REDCap-based research workflows
* Methodological prototyping
* PhD / early-career research portfolios
* Teaching latent structure discovery methods

---

## 🔗 Related Repositories

1. [**REDCap Clinical Data Pipeline (R)**](https://github.com/mnfahmi29/redcap-malueka)
2. [**Clinical Exploratory Analysis Pipeline**](https://github.com/mnfahmi29/exploratory-analysis)
3. [**Biostatistics for EHR**](https://github.com/mnfahmi29/biostat-crf)

---

## 📄 License & Citation

This project is provided for research and educational purposes.
If you reuse or adapt this workflow, please cite appropriately.

---

## 👤 Author

**Muhammad Nur Fahmi, MD**

---

