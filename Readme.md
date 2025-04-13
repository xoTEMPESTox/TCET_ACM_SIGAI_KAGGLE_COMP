
# 🔐 [System Threat Predictor – ACM SIGAI TCET Kaggle Challenge](https://www.kaggle.com/competitions/acm-sigai-tcet)

## 🏁 Overview

In an era of hyper-connected systems and ever-evolving cyber threats, the need for proactive defense mechanisms is more urgent than ever.

Welcome to **System Threat Predictor**, a Kaggle-hosted competition where your mission is to build intelligent machine learning models that can predict cybersecurity intrusions before they occur. Compete by crafting models that distinguish safe behavior from malicious attacks—**in real time**.

---

## 📝 Challenge Description

You are provided a realistic, richly annotated dataset with both:

- **📡 Network-level indicators** like protocol types, packet sizes, encryption methods  
- **👥 User behavior metrics** such as login frequency, session durations, access times, and IP reputation  

Your goal:  
🎯 **Binary classification**  
Predict the `attack_detected` column:  
- `1` = threat detected  
- `0` = normal/safe session  

---

## 💡 Use Cases

- Enterprise-grade threat detection systems  
- SOC (Security Operations Center) smart monitoring tools  
- AI-based anomaly detection firewalls  

---

## 📊 What You’ll Build

### 🔢 Classical ML Models:
- Logistic Regression
- Random Forest
- SVM
- XGBoost

### 🤖 Deep Learning Models:
- DNNs
- LSTMs for sequence-aware behavior modeling

### 🧠 Hybrid Pipelines:
- Autoencoders
- Isolation Forests
- Ensemble-based anomaly detectors

---

## ⚠️ Real-World ML Challenges

- Handling **evasion techniques** used by modern hackers  
- Managing **concept drift** in attack strategies  
- Balancing **false positives** vs **false negatives**  

Let your model be the **first line of digital defense**.

---

## 🧮 Evaluation Metric

Submissions are ranked based on the **ROC AUC** (Receiver Operating Characteristic - Area Under Curve) between predicted probabilities and true `attack_detected` values.  
This metric helps balance **sensitivity** (recall) and **specificity**.

### 📤 Submission Format:
- Format your predictions as a CSV with columns: `ID`, `TARGET`
- `TARGET` must be a float between 0 and 1 (probability of attack)

**Example:**
```
ID,TARGET  
2,0.0034  
5,0.7823  
6,0.1890  
...
```

---

## 📄 Dataset Description

Dataset is divided into three CSVs:

| File | Description |
|------|-------------|
| `train.csv` | Contains session features with labels (attack_detected) |
| `test.csv` | Contains session features without labels |
| `sample_submission.csv` | Format reference with all test `session_id`s |

### 📊 Features

| Column | Description |
|--------|-------------|
| `session_id` | Unique identifier |
| `network_packet_size` | Size of packets (64-1500 bytes) |
| `protocol_type` | TCP, UDP, ICMP |
| `login_attempts` | Login attempts during session |
| `session_duration` | Duration in seconds |
| `encryption_used` | AES, DES, or None |
| `ip_reputation_score` | 0 to 1 score (higher = more suspicious) |
| `failed_logins` | Number of failed logins |
| `browser_type` | Chrome, Firefox, Edge, Safari, Unknown |
| `unusual_time_access` | 1 if accessed at odd hours |
| `attack_detected` | **Target variable** (only in `train.csv`) |

---

## 🧠 Prediction Task

Predict the **likelihood** that each session in the test set corresponds to a cyberattack.  
Your model should output probabilities between **0 and 1**.

---

## 📘 Project Notebook Summary

Parsed Notebooks:
### [`Competition_Setup.ipynb`](./Competition_Setup.ipynb)
- EDA on network-level features like `packet_size` and `protocol_type`
- Checked correlations with `attack_detected`
- Visualizations (e.g., heatmaps, boxplots) show behavior of malicious vs normal sessions
- Started data cleaning and handling nulls in browser_type and encryption fields

### [`Priyanshu_Code.ipynb`](./Priyanshu_Code.ipynb)
- Implemented preprocessing pipeline using `LabelEncoder` for categorical features
- Trained initial models: `RandomForestClassifier` and `XGBoost`
- Included ROC-AUC evaluation with `cross_val_score`
- Set up output pipeline to generate `submission.csv` in correct format
- Feature importance visualization was done to interpret key indicators like `ip_reputation_score`, `login_attempts`

---

## 🚀 Getting Started

1. Clone the repository  
   ```bash
   git clone https://github.com/your-repo-name.git
   cd your-repo-name
   ```
2. Install required libraries  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the pipeline notebooks to explore, train, and generate submission.

---

## 📬 Submission Checklist

✅ Format matches `sample_submission.csv`  
✅ All `TARGET` values are floats between 0 and 1  
✅ ROC AUC used for evaluation  

---

## 🔐 Prevent. Predict. Protect.

Let’s build systems that safeguard the future.


