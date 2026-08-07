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

This repository contains the complete implementation for **Phase 1** of the **BCSE331L Exploratory Data Analysis Course Project**, covering data preprocessing, statistical inspection, data cleaning, feature engineering, and exploratory data analysis.

**Dataset Source**: [bank-full.csv](https://raw.githubusercontent.com/salemprakash/EDA/main/Data/bank-full.csv)

---

## 🛠️ Phase 1 Tasks & Implementation

1. **Loading the Dataset**: Loaded dataset (`bank-full.csv`, 41,188 rows × 21 columns) via pandas with `;` separator.
2. **Basic Statistical Analysis**: Computed `.shape`, `.dtypes`, summary statistics (`.describe()`), mean, median, min, max, and standard deviation.
3. **Handling Missing Data**: Checked for null values (`.isnull().sum()`) and applied mean imputation to numeric columns.
4. **Data Cleaning**: Removed 12 duplicate records (yielding 41,176 rows) and stripped whitespace from column names.
5. **Data Transformation**: Binned `age` into 4 groups (`Young`, `Adult`, `Middle`, `Senior`) and applied `log1p` transformation to `duration`.
6. **Univariate Analysis (3 Visualizations)**:
   - Age distribution (Histogram with KDE)
   - Job distribution (Countplot)
   - Call duration distribution (Boxplot)
7. **Bivariate Analysis (3 Visualizations)**:
   - Age vs Duration (Scatterplot)
   - Marital Status vs Duration (Boxplot)
   - Education Level vs Age (Boxplot)
8. **Multivariate Analysis (3 Visualizations)**:
   - Age vs Duration with Outcome `y` (Hue Scatterplot)
   - Job Category vs Age with Outcome `y` (Hue Boxplot)
   - Correlation Matrix of numeric indicators (Heatmap)

---

## 📁 Repository Structure

```
lakshya_gupta_eda/
├── Lakshya_gupta_eda.ipynb   # Jupyter Notebook containing code, outputs & visualizations
└── README.md                 # Project documentation
```

---

**Submitted by:** Lakshya Gupta (Reg No: 23BDS0290)  
**Submitted to:** Dr. M. Prakash | SCOPE | VIT Vellore
