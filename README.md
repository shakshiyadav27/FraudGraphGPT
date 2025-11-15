# FraudGraphGPT
Graph based Credit Card Fraud Detection using Node2Vec + Ensemble Models + Power BI Analysis
---

🚀 FraudGraphGPT — Advanced Credit Card Fraud Detection (Ensemble + Graph Features)

This project builds a high-performance credit card fraud detection system using an Ensemble ML model combined with graph-based features, designed for extremely imbalanced data.

✔ 97% Accuracy
✔ 92% Recall at 1% threshold
✔ AUC: 0.98
✔ Real-like dataset: 56,000+ transactions


---

📌 1. Project Overview

FraudGraphGPT predicts fraudulent transactions using a hybrid system:

🧠 Machine Learning Models

🔗 Graph Network features

📉 Threshold tuning for maximum recall

🔍 Advanced data processing + synthetic enrichment


Goal:
👉 Detect as many frauds as possible while maintaining stability on large datasets.


---

📌 2. Project Structure

FraudGraphGPT/
│── fraud_model.ipynb             # Full ML pipeline
│── FraudGraphGPT_Final.csv       # Cleaned final dataset
│── README.md                     # Documentation
│── images/
│     ├── confusion_matrix.png
│     ├── precision_recall.png
│     ├── roc_curve.png


---

📌 3. Dataset Description

Final dataset columns:

Column	Description

Transaction_ID	Unique ID per transaction
Time	Hour of transaction (0–23)
Amount	Transaction value
Card_ID	Synthetic card ID
Merchant_ID	Synthetic merchant ID
Device_ID	Synthetic device ID
Latitude, Longitude	Synthetic coordinates
Geo_Location	Random assigned city
Actual_Label	True fraud (0/1)
Predicted_Probability	Fraud probability
Predicted_Label	0/1 final decision
Threshold_Value	Best threshold chosen
Model_Name	"FraudGraphGPT Ensemble"


⚠ All ‘V1–V28’ features removed — to reduce noise and size.


---

📌 4. ML Pipeline

Step 1: Data Preprocessing

Removed negative Time & Amount

Normalized Time → 0–23

Generated synthetic Card/Merchant/Device IDs

Added location fields

Removed PCA-like V1..V28 columns



---

Step 2: Models Used

🔷 Isolation Forest

Detects anomalies based on distribution.

🔶 Autoencoder

Learns compressed representation of normal transactions.

🟧 XGBoost Classifier

Predicts final fraud label with handcrafted + graph features.


---

Step 3: Ensemble Layer

Final fraud score:

Score = 0.4 * IsolationForest + 0.3 * Autoencoder + 0.3 * XGBoost

Best Threshold = 0.01


---

📌 5. Model Results

✔ Confusion Matrix

[[56831     33]
 [   14     84]]

✔ Metrics Summary

Metric	Value

Accuracy	97%
Recall	92%
Precision	5%
AUC	0.98


⚠ Precision intentionally low — because goal = catch maximum frauds.


---

📌 6. How to Run

1️⃣ Install packages

!pip install numpy pandas scikit-learn xgboost matplotlib seaborn networkx

2️⃣ Run the notebook

Open:

FraudGraphGPT.ipynb

Run all cells.

3️⃣ Export cleaned data

Already done:

FraudGraphGPT_Final.csv


---

📌 7. How to Upload to GitHub

✔ Step 1: Create repo

GitHub → New Repository
Name → FraudGraphGPT

✔ Step 2: Upload files

Upload:

fraud_model.ipynb
FraudGraphGPT_Final.csv
README.md
images/



---

📌 8. Future Improvements

Add deep graph models (GraphSAGE, GAT)

Deploy API using FastAPI

Build a Power BI dashboard 

Integrate real-time streaming with Kafka



---

📌 9. Author

Shakshi Yadav
ML Enthusiast | Data Science Learner
Project: FraudGraphGPT
