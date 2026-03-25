
# What Drives the Price of a Used Car?

This project explores a dataset of over 400,000 used car listings to understand the key factors that influence a car's selling price. Using Python and machine learning, we identify price drivers and build predictive models to help used car dealers make better inventory and pricing decisions.

---

## Summary of Findings

- **Top Price Drivers**: Age, mileage, manufacturer (e.g., Toyota), vehicle type (e.g., pickup), condition, and transmission type.
- **Best Performing Model**: Gradient Boosting Regressor with R² = 0.85 and RMSE ≈ $2,950.
- **Key Recommendation**: Dealers should focus on low-mileage, newer vehicles from high-retention brands and price vehicles based on multiple features, not just make/model.

---

## Models Used

- Linear Regression
- Ridge and Lasso Regression (with hyperparameter tuning)
- Random Forest Regressor
- Gradient Boosting Regressor (GridSearchCV used for tuning)

---

## How to Use

1. Clone the repository or download the notebook.
2. Ensure you have `pandas`, `numpy`, `scikit-learn`, `matplotlib`, and `seaborn` installed.
3. Run the notebook top to bottom to reproduce results.
4. Review the final section for actionable business recommendations.

---

## Notebook Link

[Click here to open the notebook](http://localhost:8888/lab/workspaces/auto-8/tree/kaiserlocal/projects/ai-ml/uc-berkeley/used-card/prompt_II.ipynb)
