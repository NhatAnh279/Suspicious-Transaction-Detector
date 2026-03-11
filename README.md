# Fraud Detection Using Anomaly Detection

## Project Overview
This project explores fraud detection in banking transactions using **unsupervised anomaly detection techniques**. The dataset contains **50,000 simulated banking transactions**, and the goal is to identify unusual transaction patterns that may indicate potential fraudulent behaviour.

Since the dataset does not contain a labelled fraud column, anomaly detection methods were applied to identify suspicious transactions based on behavioural patterns.

---

## Dataset
The dataset includes **50,000 bank transactions** with features such as:

- Transaction ID  
- Account ID  
- Transaction Amount  
- Transaction Type  
- Location  
- Channel (ATM, Online, Branch)  
- Customer Age  
- Customer Occupation  
- Transaction Duration  
- Login Attempts  
- Account Balance  

These features were used to analyse transaction behaviour and detect anomalies.

---

## Methodology

### 1. Data Cleaning and Preprocessing
The dataset was prepared using Python by:

- Standardising categorical variables  
- Removing identifier columns not suitable for modelling  
- Encoding categorical variables  
- Scaling numerical features for anomaly detection models  

**Libraries used:**
- Pandas  
- NumPy  
- Scikit-learn  

---

## Model Comparison

Two anomaly detection models were tested:

- **Isolation Forest**
- **Local Outlier Factor (LOF)**

Both models identified approximately **1% of transactions as anomalies**:

- **Isolation Forest:** 496 anomalies detected  
- **Local Outlier Factor:** 500 anomalies detected  

However, the detected anomalies differed significantly between the models.

After reviewing the flagged transactions, **Isolation Forest was selected as the final model** because it identified more plausible fraud-related patterns.

---

## Key Findings

The final model detected suspicious patterns including:

- **Unusually high login attempts**
- **Transaction amounts disproportionately large relative to account balance**
- Behaviour patterns that deviate from typical transaction activity

These indicators may represent potential fraud risk and warrant further investigation.

---

## Limitations

The dataset does not contain ground-truth fraud labels.  
As a result, standard evaluation metrics such as **accuracy, precision, recall, and F1-score** could not be used.

Model performance was instead assessed based on:

- Plausibility of detected anomalies  
- Analysis of suspicious transaction patterns
