# 🚢 Titanic Survival Analysis

> **Exploring how gender, passenger class, and age determined survival aboard the RMS Titanic (1912)**

[![Top 100 — ST@40 Schull Technologies](https://img.shields.io/badge/🏆%20Top%20100-ST%4040%20Schull%20Technologies-gold?style=flat-square)](https://schull.io)
[![Python](https://img.shields.io/badge/Python-pandas%20%7C%20numpy-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat-square&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)

---

## 📋 Project Overview

This capstone project analyzes survival patterns from the RMS Titanic dataset using **Python** for data cleaning and **Microsoft Power BI Desktop** for interactive visualization. The goal was to identify which passenger characteristics most strongly predicted survival.

**Dataset:** 891 passenger records · 12 original columns  
**Author:** Furutan Samuel — 3MTT NextGen Data Science Fellow (FE/23/24424875)  
**Tools:** Python (Google Colab) · pandas · numpy · Microsoft Power BI Desktop

---

## 🔑 Key Findings

| Group | Survival Rate | Count |
|-------|:---:|:---:|
| **Female** | **74.20%** | 314 |
| Male | 18.89% | 577 |
| 1st Class | 62.96% | 216 |
| 2nd Class | 47.28% | 184 |
| **3rd Class** | **24.24%** | 491 |
| Child (0–12) | 57.97% | 69 |
| Teen (13–19) | 41.05% | 95 |
| Adult (20–59) | 36.52% | 701 |
| Senior (60+) | 26.92% | 26 |
| **Overall** | **38.38%** | **891** |

### Top Insights

1. **Gender was the strongest survival predictor** — Female passengers survived at **74.2%** vs **18.9%** for males (nearly 4× higher), consistent with "women and children first" evacuation protocols.

2. **Passenger class reflected social inequality** — 1st Class passengers survived at **63%** vs **24.2%** for 3rd Class — a gap of nearly **39 percentage points**. Lower-deck cabin locations made lifeboat access significantly harder.

3. **Children were prioritized** — Children (0–12) had the highest age-based survival rate at **57.97%**, while Seniors (60+) had the lowest at **26.92%**.

4. **3rd Class carried most passengers and lowest survival** — 55.1% of all passengers were in 3rd Class, directly pulling down the overall survival rate to 38.38%.

5. **Privilege stacked** — A female 1st Class passenger had >90% survival probability. A male 3rd Class passenger had <15%. Gender and class combined to determine who lived.

---

## 🛠️ Data Cleaning Summary

All cleaning was performed in **Python (Google Colab)** using `pandas` and `numpy`.

| Issue | Action Taken |
|---|---|
| 177 missing Age values (19.87%) | Filled with **median age (28.0)** — preferred over mean to reduce outlier effect |
| 687 missing Cabin values (77.1%) | Created `has_cabin` binary column (1/0); dropped original Cabin column |
| 2 missing Embarked values (0.22%) | Filled with mode — **'S' (Southampton)**, most frequent port |
| Age column stored as string | Converted to numeric using `pd.to_numeric(errors='coerce')` |
| Non-standard `\N` missing values | Replaced with `np.nan` before processing |

### Feature Engineering

| New Column | Description |
|---|---|
| `age_group` | Child / Teen / Adult / Senior categories |
| `family_size` | `SibSp + Parch + 1` (total family aboard) |
| `title` | Extracted from Name column (Mr, Mrs, Miss, Master, etc.) |
| `has_cabin` | Binary: 1 = had cabin record, 0 = no cabin record |

---

## 📁 Project Files

| File | Description |
|---|---|
| `titanic_capstone.py` | Full Python data cleaning script |
| `Titanic_Capstone_Furutan_Samuel.ipynb` | Google Colab notebook with step-by-step cleaning |
| `titanic_cleaned.csv` | Cleaned dataset (891 rows × 15 columns) |
| `Titanic_Report_Furutan_Samuel.docx` | Full written analysis report |
| `Titanic_Dashboard_Furutan_Samuel.pbix` | Interactive Power BI dashboard file |
| `titanic_dashboard.html` | Interactive web dashboard (Chart.js) |

---

## 📊 Dashboard

An interactive web dashboard built with Chart.js is included (`titanic_dashboard.html`).  
Open the file in any browser — no installation needed.

**Charts included:**
- Survived vs Not Survived by Gender (grouped bar)
- Survival Rate by Passenger Class (bar)
- Survival Rate by Age Group (horizontal bars)
- Survival Rate by Passenger Title (horizontal bar)
- Full statistical summary table

---

## ⚠️ Limitations

- Dataset covers only 891 of an estimated 2,224 people aboard — not all passengers are represented
- 177 missing Age values estimated using median; may introduce slight bias in age analysis
- 77.1% of Cabin values missing — limits cabin-location analysis
- Crew members not included in dataset
- Correlation ≠ causation — other unmeasured factors likely influenced outcomes

---

## 🏆 Recognition

This project was recognized in the **Top 100** of the **ST@40 Schull Technologies** data science programme.

---

## 👤 Author

**Furutan Samuel**  
3MTT NextGen Fellow · Data Science Track · Fellow ID: FE/23/24424875  
🌐 [furutansamuel.vercel.app](https://furutansamuel.vercel.app)

---

*RMS Titanic sank on April 15, 1912. This analysis is a data science study of survival patterns and does not reduce the tragedy to statistics — it uses data to understand and remember the structural inequalities of that disaster.*
