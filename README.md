# AI in Cyber Security Lab — Assignment 2

## Lab 2: Detecting Suspicious Login Activity Using Machine Learning

| Detail | Info |
|---|---|
| Course | ENSP355 — AI in Cyber Security Lab |
| University | K.R. Mangalam University, School of Engineering & Technology |
| Session | 2026–27 |
| Mapped Course Outcome | CO3 |
| Bloom's Level | L3 – Apply / L4 – Analyze |
| Total Marks | 50 |
| Platform | Google Colab / Python |
| Duration | 4 hours |

**Submitted by:**

| | |
|---|---|
| Name | Anshuman Malik |
| Roll No. | 2401010086 |
| Course | B.Tech (CSE) |
| Semester | 5th Semester |
| Section | D |
| Batch | 2024–2028 |
| University | K.R. Mangalam University |

---

## Problem Statement

Use a small numeric login-activity dataset containing failed login attempts,
login hour, new-device status and downloaded data. Clean the data, train a
Decision Tree to classify Normal / Suspicious activity, run K-Means clustering,
interpret accuracy and the confusion matrix, and test new login records.

> ⚠️ Note: No data from real accounts or networks was used — this lab uses a
> small synthetic dataset only.

## Dataset

**File:** `simple_login_activity.csv`

| Column | Meaning |
|---|---|
| `failed_logins` | Number of failed login attempts |
| `login_hour` | Hour of login (0–23) |
| `new_device` | 1 if login from a new device, else 0 |
| `download_mb` | Data downloaded in MB |
| `label` | Target — `Normal` or `Suspicious` |

## What This Lab Covers

| Question | Topic | Marks |
|---|---|---|
| Q1 | Dataset inspection and cleaning (duplicates removed, missing values filled with column median) | 5 |
| Q2 | Training / testing split — 75% train, 25% test, stratified, `random_state=42` | 5 |
| Q3 | Decision Tree training (`max_depth=4`) and evaluation — accuracy + confusion matrix | 10 |
| Q4 | K-Means clustering (k = 2, standardized features) + cluster-vs-label comparison | 10 |
| Q5 | Feature importance chart + predictions on 3 new login records | 5 |
| Q6 | False positives, false negatives, limitations and human-review rule | 5 |
| **Total** | | **50** |

## How to Run

1. Open the notebook in **Google Colab**.
2. Upload `simple_login_activity.csv` to the Colab session (or mount Drive).
3. **Runtime → Run all** — all cells run top to bottom.
4. Outputs generated: accuracy, confusion matrix, cluster summary,
   feature-importance chart, 3 new-record predictions and the saved result file.

## Results (sample / expected outputs from the lab manual)

- Missing values after cleaning: **0**
- Duplicate rows after cleaning: **0**
- Final rows: **~100**
- Training rows: **75** | Testing rows: **25**
- Decision Tree accuracy: **~88%**
- Representative confusion matrix (Normal / Suspicious): **[[19, 0], [3, 3]]**

*(Replace with your actual notebook outputs when submitting.)*

## Key Takeaways

- **False positive:** legitimate activity wrongly marked Suspicious
  (e.g. late-night work on a new device) — wastes analyst time.
- **False negative:** malicious activity wrongly marked Normal
  (e.g. a disguised attack with few obvious indicators) — can miss a real attack.
- A model below 100% accuracy is realistic — thresholds, data quality and
  human review decide operational safety. Suspicious flags should be reviewed
  by a human analyst before action.

## Files in This Repository

| File | Description |
|---|---|
| `README.md` | This file |
| `Lab_Assignment_2.ipynb` | Completed Colab notebook (code + executed outputs) |
| `simple_login_activity.csv` | Input dataset |
| `Lab2_Login_ML_Result.csv` | Cleaned dataset + results saved by the notebook |

## Submission Checklist

- [ ] Cleaned dataset summary
- [ ] Training / testing evidence
- [ ] Decision Tree accuracy and confusion matrix
- [ ] K-Means cluster summary and label comparison
- [ ] Feature-importance chart and three new-record predictions
- [ ] False-positive / false-negative discussion and saved CSV
