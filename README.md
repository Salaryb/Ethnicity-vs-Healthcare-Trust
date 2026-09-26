# Ethnicity vs. Trust in the Israeli Healthcare System

**A Data-Driven Analysis of Healthcare Perception in Israel**

## 📖 Project Overview
This project explores the underlying factors that drive public trust in the Israeli healthcare system. Moving beyond simple averages, the research utilizes machine learning techniques to determine if demographics, socioeconomic status, and physical health can accurately predict a person's trust level[cite: 1]. Ultimately, the study reveals that forcing a "one-size-fits-all" predictive model on a highly diverse society is ineffective, and that trust is driven by deeply contextual, sector-specific motives.

## 📊 Data Source
* **Dataset:** ISSP 2021 - "Health and Health Care II" (ZA No. 8000) loaded via `MD.csv`.
* **Scope:** The dataset was strictly filtered to analyze the Israeli population (`country` containing 'Israel').
* **Target Variable:** A normalized `Trust_Score` (0-100 scale) derived from respondents' confidence levels in the healthcare system.

## 🔬 Methodology
The research follows a progressive data science workflow:
1. **Data Cleaning & Engineering:** Cleaned the raw data and mapped respondents into broad ethnic categories (Ashkenazi, Mizrachi, Arab, Jewish General, Other) using specific keywords.
2. **Initial Linear Regression:** Built a baseline model using diverse data points including smoking habits, current health, sex, education, income, and ethnicity to predict trust.
3. **Recursive Feature Elimination (RFE):** Deployed a systematic, data-driven feature selection algorithm to find the "Dream Team" of predictors (testing subsets from $k=1$ to the maximum number of features).
4. **Sector-Specific Analysis:** Divided the dataset by demographic subsets (Gender, Ethnicity, Income) to test model performance locally after hitting a predictive "glass ceiling" globally. 

## 💡 Key Findings
* **The "Glass Ceiling":** When applied to the general population, the initial linear regression achieved an $R^2 \approx 0.174$. Even the algorithmic RFE feature selection hit a hard predictive ceiling of $R^2 \approx 0.182$. This indicated that demographics alone cannot explain trust on a macro level.
* **The Arab Sector ("The Socioeconomic Ladder"):** Trust in this sector is highly rational and predictable, yielding an impressive $R^2 \approx 0.455$. It strictly follows socioeconomic status, heavily driven by income and education variables. 
* **The Ashkenazi Sector ("The Disappointed Customer"):** Trust is heavily performance-based[cite: 1]. Socioeconomic factors matter less than a decline in self-reported physical health.
* **The Mizrachi Sector ("Institutional Skepticism"):** Trust here is driven less by income or health results, and more by an underlying concern regarding fairness. The strongest predictor of low trust is the expectation of not getting treatment when needed.
* **The "Chaotic" Sectors:** The model completely collapsed and failed to predict trust for specific subsets, such as Women ($R^2 \approx -0.105$) and low-income groups ($R^2 \approx -0.807$ to $-1.783$).

## 📁 Repository Files
* `EthnicityVSHealthcareSystem.ipynb`: Contains the core data loading, demographic mapping, linear regression models, RFE feature selection, and sector-specific analyses.
* `EthnicityVSHealthcareTrust.ipynb`: Contains the mapping of objective vs. subjective health correlations, ethnicity vs. religion crosstabs, and visualizations of trust against general healthcare satisfaction.

## 🛠️ Technologies Used
* **Language:** Python 3
* **Libraries:** 
  * `pandas` and `numpy` for data manipulation.
  * `matplotlib.pyplot` and `seaborn` for data visualization.
  * `scikit-learn` (`LinearRegression`, `RFE`, `train_test_split`) for predictive modeling and feature selection.
  * `pyreadstat` for statistical data reading.

## 👥 Authors
* **Ben Jaitin**
* **Ben Vann**
