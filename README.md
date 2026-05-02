# AdaGraph-HATE  
**Adaptive Graph-Aware Hybrid Ensemble for Gendered Hate Speech Detection**

---

## 📌 Overview
AdaGraph-HATE is a **graph-aware adaptive ensemble framework** designed for detecting gendered hate speech (misogyny) in social media.  
It integrates heterogeneous models (ML, DL, Transformers, LLMs) using **instance-level dynamic weighting** based on:

- Model accuracy  
- Prediction confidence  
- Inter-model correlation (graph-based diversity)

The system achieves:
- **90.02% Accuracy**
- **Macro F1: 0.7354**
- **Real-time throughput: 18,234 tweets/sec**

---

## 🚀 Key Features
- 🔗 **Graph-aware ensemble weighting**
- ⚖️ **Instance-level adaptive fusion**
- 🧠 Supports **7+ heterogeneous models**
- 🌍 **Multilingual capability**
- ⚡ **Production-ready architecture (Kubernetes, Kafka)**
- 📊 Extensive evaluation (14 models, 5 datasets)

---

## 🧠 Model Architecture

The framework consists of 5 layers:

1. **Data Preprocessing**
   - Cleaning, normalization, deduplication
2. **Feature Extraction**
   - TF-IDF (n-grams)
   - Token sequences
   - Transformer embeddings
3. **Base Models (Parallel)**
   - SVM, KNN, Logistic Regression
   - ANN, CNN
   - BERT, SBERT
4. **Adaptive Fusion (Core)**
   - Graph-aware weighting mechanism
5. **Output Layer**
   - Final prediction + confidence score

---

## ⚙️ Methodology

### Static Ensemble
\[
P_{\text{static}}(x) = \sum_{m=1}^{7} w_m^{\text{static}} P_m(x)
\]

### Adaptive Weighting
\[
w_m(x) = \text{softmax}(\alpha A_m + \beta C_m(x) + \gamma \psi(G, x, m))
\]

### Final Prediction
\[
\hat{y}(x) = \arg\max_c P_{\text{AdaGraph}}^c(x)
\]

---

## 📊 Dataset

- 5 datasets (multilingual)
- 124K+ tweets
- Class labels:
  - **Negative (0)** → Hate / Misogyny
  - **Neutral (1)** → Non-hate
  - **Positive (2)** → Supportive content

Split:
- 70% Train / 15% Validation / 15% Test

---

## 📈 Evaluation Metrics

- Accuracy
- Macro F1 (Primary)
- Class-wise F1
- Precision & Recall
- Latency (P95, P99)
- Throughput (tweets/sec)
- Memory usage

---

## 🧪 Results Summary

| Model | Accuracy | Macro F1 |
|------|--------|---------|
| SBERT | 88.92% | 0.6753 |
| AdaGraph-HATE | **90.02%** | **0.7354** |

⚠️ Trade-off:
- Higher accuracy & Macro F1
- Lower Negative class detection (important for safety)

---

## ⚡ System Performance

| Metric | Value |
|------|------|
| Throughput | 18,234 tweets/sec |
| P95 Latency | 68.4 ms |
| Cost | ~$0.19 per 1M tweets |

---

## 🏗️ Tech Stack

- Python (PyTorch, Scikit-learn)
- Transformers (HuggingFace)
- Kafka (Streaming)
- Kubernetes (Auto-scaling)
- Docker (Containerization)

---
