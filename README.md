# Credit Card Fraud Detection

![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Supervised%20Learning-blue)
![Python](https://img.shields.io/badge/Python-3.x-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Overview

A Machine Learning project that detects fraudulent credit card transactions using **Logistic Regression** and **Random Forest** algorithms. With credit card fraud rising globally — costing Europe alone €1.8 billion in 2018 — this project provides a fast and reliable automated detection system built on supervised learning.

---

## Table of Contents

- [Abstract](#abstract)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Algorithms Used](#algorithms-used)
- [Approach Design](#approach-design)
- [Applications](#applications)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Results](#results)
- [License](#license)

---

## Abstract

Credit card fraud prevention has become one of the most critical challenges in the modern digital world. As e-commerce continues to grow, fraudulent transactions are increasingly common. This project uses a Machine Learning approach — specifically supervised learning — to identify suspicious transactions. After the dataset is preprocessed, analyzed, and visualized, a confusion matrix is established. Two core algorithms — **Logistic Regression** and **Random Forest** — are applied and compared for performance.

---

## Problem Statement

- Credit card information is leaked and exploited by fraudsters.
- Cardholders are wrongly charged for unauthorized transactions.
- According to the European Central Bank, **€1.8 billion** was lost due to credit card fraud in 2018 in Europe alone.
- Automated fraud detection must be both **fast** and **reliable** to prevent damage before it occurs.
- This project leverages Machine Learning to build an effective fraud detection solution.

---

## Dataset

- **Source:** Credit card transactions from 2013 by European cardholders.
- **Size:** 284,807 records, of which only **492 are fraudulent** (0.172% — highly imbalanced).
- **Features:** 26 numerical features obtained via PCA transformation (anonymized) + 2 raw features:
  - `Time`: Seconds elapsed between transactions
  - `Amount`: Transaction amount
- **Target:** Binary label — `0` (legitimate) or `1` (fraudulent)

---

## Methodology

The project follows a **Supervised Learning** approach:

1. We have prior knowledge of the output labels (fraud vs. non-fraud).
2. Algorithms are trained and guided using labeled data.
3. Data analysis and visualization are performed on the dataset.
4. A confusion matrix is established after model training and evaluation.

---

## Algorithms Used

### Logistic Regression
- Used for **binary classification** tasks.
- Outputs probabilistic predictions — if the predicted probability exceeds the threshold (default 0.5), the transaction is classified as fraudulent (class `1`).
- Can be regularized to prevent overfitting.

### Random Forest
- An **ensemble learning** algorithm based on multiple decision trees.
- Each tree is trained on a random subset of the data; predictions are aggregated by majority vote.
- The greater the number of trees, the higher the accuracy and the lower the risk of overfitting.
- Suitable for both Classification and Regression tasks.

---

## Approach Design

1. **Preparation of Data** — Load, clean, and preprocess the dataset
2. **Applying Models** — Train Logistic Regression and Random Forest models
3. **Comparing Models** — Evaluate performance metrics side by side
4. **Evaluation** — Analyze confusion matrix, accuracy, precision, recall, and F1-score
5. **Analyse Best Model** — Select and document the best-performing algorithm

---

## Applications

Credit cards and fraud detection systems are used across many industries:

| Industry | Use Case |
|---|---|
| Warehouse Stores | In-store or online purchasing |
| Telecom Services | Mobile recharge and service payments |
| Ride-Sharing Platforms | Ride payment processing |
| Grocery Stores | Grocery bill payments |
| Restaurants | Meal bill payments |
| Online Shopping | E-commerce transactions |
| Healthcare | Medical bill payments |
| Educational Institutions | Tuition fee payments |

---

## Installation

```bash
# Clone the repository
git clone https://github.com/ahmedelbadawy2020/credit-card-fraud-detection.git

# Navigate to the project directory
cd credit-card-fraud-detection

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt
```

---

## Usage

```python
# Run the main fraud detection script
python fraud_detection.py

# Or open the Jupyter Notebook for interactive analysis
jupyter notebook Credit_Card_Fraud_Detection.ipynb
```

### Example Workflow

```python
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report, confusion_matrix

# Load dataset
df = pd.read_csv('creditcard.csv')

# Split features and target
X = df.drop('Class', axis=1)
y = df['Class']

# Train/test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train Logistic Regression
lr_model = LogisticRegression(max_iter=1000)
lr_model.fit(X_train, y_train)

# Train Random Forest
rf_model = RandomForestClassifier(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)

# Evaluate
print("Logistic Regression:")
print(classification_report(y_test, lr_model.predict(X_test)))

print("Random Forest:")
print(classification_report(y_test, rf_model.predict(X_test)))
```

---

## Dependencies

```txt
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=0.24.0
matplotlib>=3.4.0
seaborn>=0.11.0
jupyter>=1.0.0
imbalanced-learn>=0.8.0
```

Install all dependencies with:

```bash
pip install -r requirements.txt
```

---

## Results

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| Logistic Regression | ~99.9% | High | Moderate | Good |
| Random Forest | ~99.9%+ | Very High | High | Excellent |

> **Note:** Due to class imbalance (0.172% fraud rate), accuracy alone is not a reliable metric. Precision, Recall, and F1-Score are the primary evaluation metrics.

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## Author

**Ahmed Elbadawy**
- GitHub: [@ahmedelbadawy2020](https://github.com/ahmedelbadawy2020)

---

*Built with Python | Machine Learning | Scikit-learn*
