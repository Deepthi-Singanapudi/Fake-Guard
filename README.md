# 🛡️ FAKE-GUARD

### Fake Social Media Account Detection Dashboard

FAKE-GUARD is a **cybersecurity analytics dashboard** designed to identify and assess **fake social media accounts** using **behavioral risk analysis**.
The system is built as a **central monitoring tool** for agencies to quickly evaluate suspicious accounts and take action.

---

## 📌 Problem Statement

Fake social media accounts are widely used to:

* Spread misinformation
* Conduct social engineering
* Target security organizations

Manual identification is slow and ineffective at scale.
FAKE-GUARD provides an **automated, explainable, and scalable solution**.

---

## 🎯 Solution Overview

FAKE-GUARD works in **two layers**:

### 1️⃣ Batch Analysis (Offline ML Output)

* Uses precomputed ML-based risk scores
* Analyzes historical account behavior
* Displays risk level and recommended action

### 2️⃣ Dynamic Risk Assessment (Rule-Based)

* Real-time risk estimation using behavioral rules
* No ML model required at runtime
* Suitable for quick analyst investigation

---

## 🧠 Features Used (Behavioral Inputs)

The system is **privacy-preserving** and uses only behavioral indicators:

* **Total Posts** – Activity intensity
* **Average Text Length** – Message structure
* **Duplicate Ratio** – Repetitive behavior

Raw message content is **never stored or analyzed**.

---

## 🗂️ Dataset Description

The original dataset contains **post-level data**:

* `fake_account.csv`
* `legitimate_account.csv`

Each record represents a **single post** with:

* `user_id`
* `text`

These were **aggregated into account-level features** during preprocessing.

---

## ⚙️ Data Preprocessing & Feature Engineering

Steps performed:

1. Data cleaning and encoding handling
2. Labeling fake vs legitimate accounts
3. Aggregating post-level data → account-level behavior
4. Feature extraction:

   * total_posts
   * avg_text_length
   * duplicate_ratio

---

## 📊 Risk Scoring Logic

To ensure clear differentiation, FAKE-GUARD applies:

* Log scaling
* Feature amplification
* Percentile-based normalization

This produces a **0–100 operational risk score**:

* **High Risk** → Immediate action
* **Medium Risk** → Manual review
* **Low Risk** → No action

---

## 🖥️ User Interface

The dashboard includes:

* KPI cards (High / Medium / Low risk counts)
* Account selection panel
* Risk score visualization
* Behavioral indicators
* Recommended action
* Top high-risk accounts table

Designed to resemble a **real security operations dashboard**.

---

## 🚀 Deployment

The project is deployed using **Streamlit Community Cloud**.

### Files required:

```
app.py
fake_guard_results.csv
requirements.txt
```

### `requirements.txt`

```
streamlit
pandas
numpy
```

---

## 🛠️ How to Run Locally

```bash
pip install streamlit pandas numpy
streamlit run app.py
```

---

## 🔐 Why This Approach Works

* Platform-agnostic (Facebook, Instagram, X, etc.)
* Scalable and fast
* Privacy-preserving
* Explainable decisions
* Real-world cybersecurity alignment


## 🎤 One-Line Summary (For Judges)

> “FAKE-GUARD converts social media behavior into actionable intelligence for rapid fake account detection.”

## 📌 Project Status

✔ Data preprocessing completed
✔ Feature engineering completed
✔ Risk scoring implemented
✔ Dashboard deployed
✔ Ready for evaluation
