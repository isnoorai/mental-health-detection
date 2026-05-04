# Mental Health Detection from Social Media Posts
### **Team MARS** | CSS 324: Introduction to Machine Learning
**Instructor:** Zhaniya Medeuova  
**Date:** May 4, 2026

---

## 👥 Team Members
* **230183088** — Sandygaliyev Ramazan
* **230183099** — Batyrova Makhabbat
* **230183029** — Abildayeva Merey
* **230183072** — Aidaraly Nuraiym
* **230101080** — Ramazanova Rauza

---

## 🎯 Project Overview
This project implements an advanced Machine Learning pipeline to classify social media text into seven mental health categories. By analyzing the language patterns in user posts, the system identifies potential risks and categorizes them to facilitate early intervention.

### **The Clinical Constraint**
In mental health monitoring, a **False Negative** (missing a person in crisis) is far more critical than a False Positive. Following the project requirements, we prioritized **Recall** over overall accuracy:
* **Target Suicidal Recall:** ≥ 0.90
* **Target Depression Recall:** ≥ 0.85

---

## 🛠️ Technical Pipeline

### 1. Dataset & Preprocessing
* **Source:** Combined Mental Health Dataset (approx. 53,000 samples).
* **7 Classes:** Normal, Depression, Suicidal, Anxiety, Stress, Bipolar, and Personality Disorder.
* **8-Step Cleaning:** Includes Unicode normalization, contraction expansion, and noise removal. We preserved emotional markers by avoiding aggressive lemmatization.

### 2. Feature Engineering
We used a hybrid approach to capture both context and specific risk keywords:
* **TF-IDF (1,2 n-grams):** For statistical word frequency.
* **Suicide Lexicon:** A custom feature set identifying high-risk vocabulary.
* **Deep Embeddings:** SBERT and MentalBERT for deep semantic understanding.

### 3. Machine Learning Models
To handle class imbalance and maximize recall, we experimented with:
* **Gradient Boosting:** LightGBM and CatBoost.
* **Sampling:** SMOTE (Synthetic Minority Over-sampling Technique) to balance minority classes.
* **Final Architecture:** A **Stacking Ensemble** that combines multiple models for robust prediction.

---

## 📊 Final Performance
Our final model successfully surpassed the clinical constraints:

| Metric | Target | **Result** | Status |
| :--- | :--- | :--- | :--- |
| **Suicidal Recall** | 0.90 | **0.91** | ✅ |
| **Depression Recall** | 0.85 | **0.87** | ✅ |
| **Macro F1-Score** | - | **0.82** | ✅ |

---

## 🚀 Installation & Usage

### **1. Setup Environment**
Clone the repository and install the necessary dependencies:
```bash
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
pip install -r requirements.txt
