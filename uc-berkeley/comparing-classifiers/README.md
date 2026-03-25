# Assignment 17.1: Comparing Classification Models for Bank Marketing

## Overview
This project compares the performance of four supervised machine learning classifiers:

- K-Nearest Neighbors (KNN)
- Logistic Regression
- Decision Tree
- Support Vector Machine (SVM)

The goal is to evaluate how effectively each model predicts whether a customer will subscribe to a bank product based on historical marketing campaign data. The analysis focuses on model performance, interpretability, and suitability for real-world business decision-making.

This work was completed as part of **Required Assignment 17.1: Comparing Classifiers**.

---

## Business Problem
A Portuguese banking institution conducted multiple telephone-based marketing campaigns to promote financial products. These campaigns are costly and time-sensitive, so the bank wants to improve targeting efficiency.

**Objective:**  
Predict whether a customer will subscribe to a bank product (`yes` or `no`) based on demographic, financial, and campaign-related features.

Accurate predictions can help:
- Reduce unnecessary outreach
- Increase conversion rates
- Optimize future marketing strategies

---

## Data Source
The dataset is sourced from the **UC Irvine Machine Learning Repository** and contains results from multiple direct marketing campaigns conducted via phone calls.

- Origin: Portuguese banking institution
- Target variable: `y` (subscription outcome)
- Feature types: Categorical and continuous variables related to customer profile and campaign history

Dataset link (as referenced in the assignment):  
Required Assignment 17.1 – UC Irvine Machine Learning Repository

---

## Project Structure
```
├── README.md
├── comparing_classifiers.ipynb
└── data/
    └── bank_marketing.csv
```

- `README.md`: Project summary and findings
- `comparing_classifiers.ipynb`: Jupyter Notebook containing data preparation, modeling, evaluation, and analysis
- `data/`: Folder containing the dataset

---

## Methodology

### 1. Data Preparation
- Loaded and inspected the dataset
- Handled categorical variables using appropriate encoding techniques
- Scaled numerical features where required
- Split data into training and testing sets

### 2. Exploratory Data Analysis
- Analyzed distributions of key features
- Examined relationships between predictors and the target variable
- Identified class imbalance in the response variable

### 3. Modeling
The following models were trained and evaluated:

- **K-Nearest Neighbors (KNN)**
- **Logistic Regression**
- **Decision Tree**
- **Support Vector Machine (SVM)**

Each model was evaluated using:
- Cross-validation
- Hyperparameter tuning (GridSearch where applicable)
- Performance metrics aligned with the business goal

---

## Evaluation Metrics
Because the dataset is imbalanced and the business goal prioritizes identifying potential subscribers, the following metrics were emphasized:

- Accuracy
- Precision
- Recall
- F1-score

**Recall** was especially important to minimize missed opportunities for successful subscriptions.

---

## Results Summary
- **Logistic Regression** provided strong baseline performance with good interpretability and balanced recall.
- **Decision Trees** captured non-linear patterns but showed signs of overfitting.
- **KNN** was sensitive to feature scaling and computationally less efficient.
- **SVM** achieved competitive accuracy but required more tuning and offered limited interpretability.

Overall, **Logistic Regression** delivered the best balance between performance, speed, and interpretability for this business use case.

---

## Key Findings
- Customer subscription behavior is influenced by both demographic and campaign-specific factors.
- Simpler models can perform comparably to more complex ones when properly tuned.
- Model interpretability is crucial for business adoption in marketing contexts.

---

## Recommendations
- Use **Logistic Regression** as the primary model for deployment due to its transparency and reliable performance.
- Incorporate recall-focused evaluation when optimizing future models.
- Explore ensemble methods (e.g., Random Forest, Gradient Boosting) as a next step.
- Collect additional behavioral and temporal features to further improve predictions.

---

## Next Steps
- Address class imbalance using resampling techniques
- Test ensemble and boosting models
- Integrate model predictions into marketing campaign workflows
- Monitor model performance over time with new campaign data

---

## Notebook Link
[Click here to open the notebook](http://localhost:8888/lab/tree/kaiserlocal/projects/ai-ml/uc-berkeley/comparing-classifiers/prompt_II.ipynb)

📘 `comparing_classifiers.ipynb`

---
