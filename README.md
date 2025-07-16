# KeepUp-A-unified-framework-and-Dataset
This is the official repository of "KeepUp: A Unified Framework Fusing Knowledge Extraction, Social Platform Engagement, and User Profiling for Fake News Detection"

# 📰 Fake News Detection Pipeline

This project implements a multi-stage pipeline to detect fake news using document retrieval, entailment analysis, stance detection, and user feature integration.

---

## 📁 Dataset Structure

The dataset is provided in a compressed format and contains the following files:

### 1. `evidence.zip`
- Contains multiple documents used for evidence retrieval during the initial stage.

### 2. `claims.csv`
- A CSV file listing various claims that need to be verified using retrieved evidence.

### 3. `dataset.xlsx`
An Excel file consisting of the following sheets:
- **Claims** – Metadata and details about each claim.
- **Post Features** – Features extracted from associated social media posts.
- **User Features** – Information about users such as credibility scores and activity history.
- **Comments** – User comments related to each post.

---

## 🧠 Pipeline Overview

### 🔍 1. Document Retrieval
- **Input:** `claims.csv` + documents from `evidence.zip`
- **Output:** A file containing top relevant documents per claim.
- **Goal:** Retrieve potential evidence for each claim.

---

### 🔗 2. Entailment Task
- **Input:** Output from the Document Retrieval step.
- **Task:** Perform natural language inference (NLI) to determine if the evidence supports, refutes, or is unrelated to the claim.

---

### 📣 3. Stance Detection
- **Input:** `Comments` and `Post Titles` from `dataset.xlsx`
- **Task:** Classify stance of each comment and title towards its claim (e.g., **agree**, **disagree**, **discuss**, or **unrelated**).

---

### 👤 4. User Feature Extraction
- **Input:** Post titles + data from `User Features` sheet.
- **Task:** Derive new user-level features from titles and combine them with existing features for each user.

---

### 🚨 5. Fake News Detection
- **Input:** Aggregated features from entailment, stance, and user data.
- **Task:** Perform final classification to determine whether a claim is **fake** or **real**.

---

## 🛠️ Technologies Used
- Python
- Pandas / NumPy
- scikit-learn
- TensorFlow / PyTorch (for NLI or stance detection models)
- Natural Language Processing (NLP)

---

## ✅ Conclusion

This modular pipeline combines multiple layers of reasoning and user behavior analysis to deliver a robust fake news detection system.


