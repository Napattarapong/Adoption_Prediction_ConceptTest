# 🐾 Pet Adoption Speed Prediction

<div align="center">

![Status](https://img.shields.io/badge/Status-Phase%201%20Completed-success)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Metric](https://img.shields.io/badge/Current%20Accuracy-37.16%25-red)

**An experimental machine learning project to predict how quickly a pet will find a new home based on its profile data.**

</div>

---

## 📊 Phase 1: Tabular Data Analysis
In this initial phase, the model was trained exclusively on **Structured Data (Tabular)** extracted from the dataset. The primary focus was to establish a baseline performance using physical and health attributes.

### 🧬 Features Used
* **Physical:** Breed, Color, Age, Fur Length, Gender
* **Health:** Vaccinated, Dewormed, Sterilized, Health Condition
* **Meta:** Quantity, Fee

### 📉 Current Performance Overview
The model (**Random Forest Classifier**) achieved an accuracy of **37.16%** on unseen data.

| Metric | Score | Note |
| :--- | :---: | :--- |
| **Accuracy** | `0.3716` | Slightly better than random guessing (20%) but not optimal. |
| **Best Class** | `Class 4` | **Recall: 57%** (Pets waiting >100 days) - Model is biased towards this class. |
| **Worst Class** | `Class 0` | **Recall: 4%** (Pets adopted same day) - Model fails to detect quick adoptions. |

> [!WARNING]
> **Critical Insight:** The model suffers from severe **Class Imbalance**. It performs well on the majority class (Class 4) but struggles significantly with the minority class (Class 0), resulting in low overall predictive power for fast adoptions.

---

## 🧐 Why is the accuracy low? (Limitation Analysis)

The current experiment highlights a fundamental limitation: **"Adoption is Emotional."**

Using only tabular data (numbers and categories) misses the **human element** of the adoption process. The model currently **cannot see** what the potential owner sees:
1.  **No Visual Context:** It doesn't know if the pet looks cute, friendly, or sad (Images).
2.  **No Narrative Context:** It doesn't read the heartwarming or urgent story behind the pet (Text Description).

Therefore, the model is trying to guess "likability" based purely on statistics like Age and Breed, which is insufficient.

---

## 🚀 Roadmap: Future Improvements

To bridge the gap between data and human emotion, the next iterations will evolve into a **Multi-Modal Learning** system.

### ✅ Phase 2: NLP Integration (Next Step)
* **Goal:** Incorporate the `Description` field.
* **Technique:** Utilize **TF-IDF** or **Word Embeddings (BERT)** to extract sentiment and keywords (e.g., "urgent", "playful", "injured").
* **Expected Outcome:** Better differentiation between pets with similar physical stats but different stories.

### 🖼️ Phase 3: Computer Vision Integration
* **Goal:** Incorporate `Profile Images`.
* **Technique:** Use CNNs (Convolutional Neural Networks) to extract visual features.
* **Expected Outcome:** Capture the "Cuteness Factor" and image quality, which are strong drivers for click-through rates.

---

<div align="center">

*Created with ❤️ for PetFinder Kaggle Competition / University Project*

</div>
