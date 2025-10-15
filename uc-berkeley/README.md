# Amazon Coupon Acceptance Analysis

This repo explores **who accepts location-based coupons** using the UCI “In-vehicle coupon recommendation” dataset.

- **Notebook:** [`prompt.ipynb`](prompt.ipynb)
- **Data (assumed path):** `./data/coupons.csv`

> Goal: Use quick EDA and simple slices to understand which passengers are most likely to accept coupons (with **Bar** and **Coffee House** examples).

---

## Dataset

- **File:** `./data/coupons.csv` (assumed to exist locally in the `data/` folder)
- **Shape (after load):** ~12.7k rows × 26 columns
- **Duplicates:** ~74 rows

> If you place the CSV elsewhere, update the `pd.read_csv()` line in the notebook accordingly.

---

## How to run

1. Create/activate a Python 3.11+ environment.
2. Install basics:
   ```bash
   pip install pandas matplotlib seaborn jupyter
   ```
3. Put the dataset at `./data/coupons.csv`.
4. Launch the notebook:
   ```bash
   jupyter notebook prompt.ipynb
   ```
5. Localhost URL link:
   http://localhost:8888/lab/tree/ai-ml/uc-berkeley/amazon-coupon/prompt.ipynb

---

## Key findings (high level)

### Bar coupons
- **Habit strength matters.** Regular bar-goers are far more likely to accept:
  - ≤3×/month: **~52.8%**
  - >3×/month: **~76.9%**
- **Age + frequency:** Among >1×/month visitors, **age >25** accept at **~70.0%**, vs **~34.8%** for everyone else.
- **Interpretation:** Bar coupons act as a nudge for an existing habit, not a trigger for new behavior.

### Coffee House coupons
- **Overall acceptance:** **~49.9%**.
- **Visit frequency (self‑reported “CoffeeHouse”):** acceptance is highest for **4–8/month** segments (**~68.6%**).
- **Time of day:** **10AM** shows elevated acceptance (**~64.1%**).
- **With friends:** Riding with **Friend(s)** has higher acceptance (**~59.7%**).
- **Expiration:** **1‑day** expiry performs better (**~58.4%**) than longer windows (urgency effect).

> These segment cuts come from simple group-bys; they highlight correlations, not causality.

---

## Reproducibility notes

- The notebook assumes the dataset at `./data/coupons.csv`. If the CSV isn’t found, update the path or place the file in `data/`.
- A small plotting fix is included so seaborn can read the missingness table (reset index before plotting).

---

## Files

- `prompt.ipynb` — main analysis notebook
- `data/coupons.csv` — input dataset (not committed here; place it locally)
- `README.md` — this file

---
