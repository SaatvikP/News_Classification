# 📰 News Classification using BiLSTM and GloVe Embeddings

## 📌 Project Overview
This project implements **text classification** using a **Bidirectional LSTM (BiLSTM)** model with **pre-trained GloVe embeddings**. Two datasets are used:

1. **20 Newsgroups Dataset** (20 categories)
2. **AG News Dataset** (4 categories)

The goal is to **classify news articles into predefined categories** using **deep learning-based NLP techniques**.

---

## 📂 **Datasets**
### 🏷 **1. 20 Newsgroups Classification**
- Classifies news articles into **20 distinct categories**.
- Dataset obtained via `fetch_20newsgroups` from `scikit-learn`.
- Categories include: *alt.atheism, comp.graphics, rec.sport.baseball, sci.med*, etc.

### 🌍 **2. AG News Classification**
- Classifies news headlines into **4 broad categories**: 
  - **World**
  - **Sports**
  - **Business**
  - **Science/Technology**
- Dataset obtained from `datasets` library.

---

## 🛠 **Preprocessing Steps**
✔ **Tokenization**: Used `Keras Tokenizer` with vocab sizes **20,000** (20 Newsgroups) and **10,000** (AG News).  
✔ **Padding**: Sequences padded to **200 tokens** (20 Newsgroups) and **50 tokens** (AG News).  
✔ **Label Encoding**: One-hot encoding applied for multi-class classification.  

---

## 🏗 **Model Architecture**
A **Bidirectional LSTM (BiLSTM) network** is used with **GloVe word embeddings**:
1. **Embedding Layer** – Uses **pre-trained 100-dimensional GloVe embeddings**.
2. **BiLSTM Layer** – 128 LSTM units with dropout (0.4).
3. **Dense Layer** – 64 neurons (ReLU activation) + Dropout (0.5).
4. **Output Layer** – 
   - **Softmax** activation for **multi-class classification**.

---

## 🏋️ **Training and Optimization**
- **Batch Size**: 32
- **Early Stopping**: Stops if validation loss does not improve after 3 epochs.
- **Validation Split**: 10% of training data.

---

## 📊 **Evaluation Results**
### **📌 20 Newsgroups (20 Categories)**
| Metric         | Score |
|---------------|-------|
| Accuracy      | 57%  |
| Precision     | 54%  |
| Recall        | 55%  |
| F1 Score      | 54%  |

### **📌 AG News (4 Categories)**
| Metric         | Score |
|---------------|-------|
| Accuracy      | 91%  |
| Precision     | 91%  |
| Recall        | 91%  |
| F1 Score      | 91%  |

---
