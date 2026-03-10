# 🎱 Greek Joker Lottery — Statistical Fairness Analysis

A rigorous, end-to-end statistical investigation of the **Greek Joker lottery** (1997–2024) using 27+ years of official OPAP historical draw data.

---

## 🔍 Project Overview

This project applies a battery of classical and simulation-based statistical tests to answer one question:

> **Is the Greek Joker lottery a random process?**

13 independent tests cover number frequency, draw structure, serial dependence, pairwise independence, and jackpot outcome calibration.

---

## 📊 Tests & Methods

| # | Test | Method | Scope |
|---|------|--------|-------|
| 1 | Main number uniformity | χ² goodness-of-fit | All years combined |
| 2 | Joker number uniformity | χ² goodness-of-fit | All years combined |
| 3 | Year-by-year uniformity | χ² + Bonferroni correction | Each year |
| 4 | Draw sum distribution | Kolmogorov-Smirnov vs 100k simulations | All draws |
| 5 | Odd/Even balance | KS test vs simulation | All draws |
| 6 | High/Low balance | KS test vs simulation | All draws |
| 7 | Pairwise co-occurrence | χ² on 990 number pairs | All draws |
| 8 | Serial autocorrelation | Ljung-Box Q-test (lags 1–20) | Full time series |
| 9 | Temporal drift | Rolling χ² (50-draw window) | Full time series |
| 10 | Jackpot win vs ticket sales | KS test | 2003–2024 |
| 11 | Rollover streak distribution | KS vs geometric distribution | 2003–2024 |
| 12 | Win/rollover calibration | Poisson test | 2003–2024 |

---

## 📁 Repository Structure

```
.
├── LotteryAnalysis.ipynb   # Main analysis notebook
├── README.md
└── data/
    └── Joker_<year>.xlsx   # Raw OPAP draw files (not included — see Data section)
```

---

## 🗂 Data

Data is sourced from [OPAP S.A.](https://www.opap.gr) official historical records. Each year is stored as a separate `.xlsx` file (`Joker_YYYY.xlsx`).

---

## 🧰 Requirements

```bash
pip install pandas numpy matplotlib scipy statsmodels openpyxl
```

| Package | Version |
|---------|---------|
| Python | ≥ 3.9 |
| pandas | ≥ 1.5 |
| numpy | ≥ 1.23 |
| matplotlib | ≥ 3.6 |
| scipy | ≥ 1.9 |
| statsmodels | ≥ 0.13 |
| openpyxl | ≥ 3.0 |


---

## 📈 Key Results

After 13 independent statistical tests, **no credible evidence of non-randomness** was found.

- Number frequencies (main 1–45 and joker 1–20) are consistent with uniform distributions.
- No year shows significant deviation after correcting for multiple comparisons.
- Draw sums, odd/even splits, and high/low splits all match theoretical expectations.
- Number pairs appear independently of each other.
- No serial correlation exists between consecutive draws.
- Jackpot win rates align precisely with the expected probability from ticket sales.

The single year (2000) that initially appeared anomalous was **not significant after Bonferroni correction**.

---




