# E-Commerce Fraud Anomaly Detection

This project implements a machine learning approach to detect fraudulent transactions in an e-commerce environment. Using the **Isolation Forest** algorithm, the model identifies suspicious patterns and outliers that deviate from standard consumer behavior.

## Project Overview
Fraud detection is a critical challenge for online retailers. This project focuses on:
* **Detection:** Using unsupervised learning to flag anomalies without needing labeled "fraud" data for every case.
* **Accuracy:** Implementing feature engineering to capture the nuances of fraudulent activity.
* **Scalability:** Building a pipeline that can handle large datasets using efficient Python libraries.

## Feature Engineering
To increase the reliability of the predictions, I engineered several key features:
* **`seconds_since_signup`**: Measures the time between account creation and purchase.
* **`device_count`**: The number of unique user IDs associated with a specific device.
* **`ip_count`**: The number of transactions linked to a single IP address.
* **`age` & `purchase_value`**: Standard demographic and transactional data used to baseline "normal" behavior.

## Technical Stack
* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `PYOD` (Isolation Forest), `matplotlib`, `seaborn`.
* **Tools:** Jupyter Notebook, Anaconda, GitHub Desktop.

## Model Implementation
The core of this project uses the **Isolation Forest** algorithm.
* **Contamination Rate:** Set to 0.1 (assuming 10% of the data contains anomalies).
* **Random State:** 42 for reproducibility of results.

```python
# Quick look at the model setup
from sklearn.ensemble import IsolationForest
model = IsolationForest(contamination=0.1, random_state=42)
model.fit(X_train)
