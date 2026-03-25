# Amazon Coupon Acceptance Analysis

This repo explores **who accepts location-based coupons** using the UCI “In-vehicle coupon recommendation” dataset.

- **Notebook:** [`prompt.ipynb`](prompt.ipynb)
- **Data file path:** `./data/coupons.csv`

---

## Dataset

- **File:** `./data/coupons.csv`
- **Shape (after load):** ~12.7k rows × 26 columns
- **Duplicates:** ~74 rows
  
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

### Hypothesis: Habitual bar-goers (especially 25+ adults) drive acceptance

- Drivers who visit bars regularly are the ones most likely to redeem bar coupons, with acceptance jumping from about 52.81% (<=3/month) to 76.88% (>3×/month). 
- Among people who go more than once a month, being over 25 further boosts acceptance to 69.97% versus 34.82% for everyone else. 
- In short, the coupon works best as a nudge for an existing habit rather than a trigger for a new behavior.

### Bar coupons
- **Habit strength matters.** Regular bar-goers are far more likely to accept:
  - ≤3×/month: **~52.8%**
  - >3×/month: **~76.9%**
- **Age + frequency:** Among >1×/month visitors, **age >25** accept at **~70.0%**, vs **~34.8%** for everyone else.
- **Interpretation:** Bar coupons act as a nudge for an existing habit, not a trigger for new behavior.

### Coffee House coupons
- **Overall Coffee House Coupon Acceptance:** **~43.10%**.
- **Time of day:** **6PM** shows maximum percentage of visitors (**~28.01%**).
- **Maximum Coupon Accepted Time:** **6PM** shows maximum percentage of coupons accepted (**~31.92%**).
- **Friends Passanger:** Riding with a Friends Passanger has coupons higher acceptance (**~55.82%**).
- **Expiration:** **2‑hour** expiry performs better (**~54.93%**) than longer windows **1‑day** (urgency effect).
  
---

## Files

- `prompt.ipynb` — main analysis notebook
- `data/coupons.csv` — input dataset (not committed here; place it locally)
- `README.md` — this file

---
