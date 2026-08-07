# Exploratory Data Analysis (EDA) Course Project — Phase 1

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/2005lakshya/lakshya_gupta_eda/blob/main/Lakshya_gupta_eda.ipynb)
[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Phase%201-Completed-success.svg)]()

---

## 📌 Student & Course Information

| Parameter | Details |
| :--- | :--- |
| **Student Name** | **Lakshya Gupta** |
| **Registration Number** | **23BDS0290** |
| **Course Code & Name** | **BCSE331L / BCSE331P — Exploratory Data Analysis Lab** |
| **Class Number / Slot** | **VL2026270103090 — L11+L12** |
| **Venue** | **SJT419** |
| **Department / School** | School of Computer Science and Engineering (SCOPE) |
| **Institution** | Vellore Institute of Technology (VIT), Vellore |
| **Faculty In-Charge** | **Dr. M. Prakash**, M.E., Ph.D., SM IEEE (Associate Professor, SCOPE) |

---

## 🎯 Project Overview & Objective

This repository contains the complete implementation for **Phase 1** of the **BCSE331L Exploratory Data Analysis Course Project**. The primary goal is to perform end-to-end data preprocessing, statistical inspection, data cleaning, feature engineering/transformation, and comprehensive exploratory data analysis (Univariate, Bivariate, and Multivariate) on the assigned dataset.

### 📊 Dataset Details
- **Dataset Name**: Bank Marketing Dataset (`bank-full.csv`)
- **Source**: Shared via course repository `https://raw.githubusercontent.com/salemprakash/EDA/main/Data/bank-full.csv`
- **Delimiter**: Semicolon (`;`)
- **Initial Shape**: 41,188 rows × 21 columns
- **Domain**: Banking & Direct Marketing Campaigns (Predicting term deposit subscription `y`)

---

## 🛠️ Phase 1 Tasks & Implementation Summary

All 8 mandatory tasks prescribed for Phase 1 have been implemented, verified, and documented:

```
┌────────────────────────────────────────────────────────────────────────────┐
│                             EDA Phase 1 Workflow                           │
└────────────────────────────────────────────────────────────────────────────┘
        │
        ├── 1. Loading the Dataset (Pandas read_csv with delimiter ';')
        ├── 2. Basic Statistical Analysis (.shape, .dtypes, .describe(), metrics)
        ├── 3. Handling Missing Data (Checking nulls, numeric mean imputation)
        ├── 4. Data Cleaning (Duplicate removal, column whitespace stripping)
        ├── 5. Data Transformation (Age binning, log transform on duration)
        ├── 6. Univariate Analysis (3+ Visualizations: Histplot, Countplot, Boxplot)
        ├── 7. Bivariate Analysis (3+ Visualizations: Scatterplot, Boxplots)
        └── 8. Multivariate Analysis (3+ Visualizations: Hue Scatter, Hue Boxplot, Heatmap)
```

---

### Detailed Task Breakdown

#### 1. Loading the Dataset
- Loaded directly from the official remote URL using `pd.read_csv(url, sep=';')`.
- Initialized DataFrame `bank_data` with shape `(41188, 21)` and previewed the initial records.

#### 2. Basic Statistical Analysis
- Inspected dataset dimensions (`41188` records, `21` attributes).
- Analyzed attribute data types (`int64`, `float64`, and `object`).
- Computed 5-number summaries and parametric statistics:
  - Comprehensive statistical tables (`.describe()` and `.describe(include='all')`).
  - Key metrics: Mean Age (~40.02 yrs), Median Duration (180.0s), Max Duration (4918s), Min Duration (0s), Std Dev of Duration (259.28s).

#### 3. Handling Missing Data
- Checked for `NaN`/null values across all columns using `.isnull().sum()`.
- Implemented mean imputation on all numeric features (`int64`, `float64`) using `fillna()`.
- Re-verified post-imputation integrity ensuring 0 missing values.

#### 4. Data Cleaning
- Detected and removed 12 duplicate records via `drop_duplicates(inplace=True)`, yielding a cleaned dataset of **41,176 records**.
- Stripped unnecessary leading and trailing whitespace from column identifiers using `columns.str.strip()`.

#### 5. Data Transformation & Feature Engineering
- **Categorical Binning**: Created `age_group` by binning `age` into 4 distinct groups:
  - `Young` (0–30), `Adult` (31–45), `Middle` (46–60), and `Senior` (61–100).
- **Logarithmic Transformation**: Engineered `log_duration` via `np.log1p(duration)` to normalize the right-skewed distribution of call durations.

#### 6. Univariate Analysis (3 Visualizations)
1. **Age Distribution**: Histogram with Kernel Density Estimation (KDE) showing client age spread (peaks around 30–40 years).
2. **Job Category Distribution**: Categorical countplot highlighting predominant professions (e.g., admin., blue-collar, technician).
3. **Call Duration Distribution**: Vertical boxplot highlighting the spread and identifying long call outliers.

#### 7. Bivariate Analysis (3 Visualizations)
1. **Age vs Duration**: Scatter plot examining relationship and clustering between customer age and call duration.
2. **Marital Status vs Duration**: Boxplot comparing call duration patterns across marital categories (`married`, `single`, `divorced`, `unknown`).
3. **Education Level vs Age**: Boxplot showing the demographic age distribution across different education tiers (`basic.4y`, `high.school`, `university.degree`, etc.).

#### 8. Multivariate Analysis (3 Visualizations)
1. **Age vs Duration segmented by Subscription Outcome (`y`)**: Scatter plot with hue mapping indicating successful term deposit conversions (`yes`/`no`).
2. **Job Category vs Age segmented by Subscription Outcome (`y`)**: Boxplot evaluating conversion patterns across various job types and age groups.
3. **Correlation Matrix Heatmap**: Heatmap with annotated Pearson correlation coefficients across all numeric variables (economic indicators: `euribor3m`, `emp.var.rate`, `nr.employed`, etc.).

---

## 📈 Key Insights from Phase 1 EDA

- **Call Duration is Strongly Correlated with Deposit Success**: Clients with higher duration phone calls show a substantially higher likelihood of subscribing (`y = yes`).
- **Demographics**: The majority of targeted clients are between 30 and 45 years old, primarily working in `admin.`, `blue-collar`, and `technician` roles.
- **Economic Indicators**: High collinearity is observed among economic parameters (`emp.var.rate`, `euribor3m`, and `nr.employed`), reflecting macroeconomic trends during the campaign period.

---

## 📁 Repository Structure

```
lakshya_gupta_eda/
├── Lakshya_gupta_eda.ipynb   # Complete Jupyter Notebook containing code, outputs & visualizations
└── README.md                 # Project documentation and submission details
```

---

## 💻 How to Run the Notebook

### Option 1: Google Colab (Recommended)
1. Click the **Open In Colab** badge at the top or click [here](https://colab.research.google.com/github/2005lakshya/lakshya_gupta_eda/blob/main/Lakshya_gupta_eda.ipynb).
2. Run all cells sequentially via `Runtime` -> `Run all` (or `Ctrl + F9`).

### Option 2: Local Environment
1. Clone the repository:
   ```bash
   git clone https://github.com/2005lakshya/lakshya_gupta_eda.git
   cd lakshya_gupta_eda
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook Lakshya_gupta_eda.ipynb
   ```

---

## 📜 Submission Checklist Verification

- [x] Dataset loaded successfully from remote URL (`bank-full.csv`)
- [x] Basic statistical analysis computed and displayed
- [x] Missing data checked and imputed
- [x] Duplicate records cleaned and column names formatted
- [x] Data transformations (binning + log scaling) implemented
- [x] Univariate analysis with **3 visualizations** generated and visible
- [x] Bivariate analysis with **3 visualizations** generated and visible
- [x] Multivariate analysis with **3 visualizations** generated and visible
- [x] Jupyter notebook properly executed with all rendered chart outputs saved
- [x] Public GitHub repository with clean documentation

---

**Submitted by:** Lakshya Gupta (Reg No: 23BDS0290)  
**Submitted to:** Dr. M. Prakash | SCOPE | VIT Vellore
