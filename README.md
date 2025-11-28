## 📊 Data Sources

### **Transactions Data**
### **Behavior Data**

## 🧹 Data Preprocessing

## 🧠 Models Used

### 1️⃣ **Unsupervised Model: LSTM Autoencoder (Anomaly Detection)**
#### Why LSTM Autoencoder?
- It learns normal transaction patterns  
- Reconstruction error becomes the **anomaly score**  
- Higher scores indicate unusual or suspicious behavior  

#### Pipeline:
1. Normalize numerical variables  
2. Create sequences for LSTM input  
3. Build Autoencoder with:
   - LSTM encoder  
   - Bottleneck layer  
   - LSTM decoder  
4. Train on **normal transactions only**  
5. Compute reconstruction error per record  
6. Plot distribution of anomaly scores  
7. Compare fraud vs. non-fraud anomaly distributions  

This allows hybrid detection:
- XGBoost → supervised fraud detection  
- LSTM → anomaly scoring of unusual behavior  

### 2️⃣ **Supervised Model: XGBoost Classifier**
Used for predicting whether a transaction is fraudulent (binary classification).

Pipeline:
- Train/test split  
- Fit `XGBClassifier`  
- Evaluate using:
  - ROC-AUC  
  - Average Precision Score  
  - Precision-Recall Curve  
- Extract top feature importances  
- Visualize PR curve  
---

## 📈 Model Evaluation

### **XGBoost**
- Strong ROC-AUC performance  
- PR-AUC suitable for imbalanced data  
- Feature importance highlights key behavioral and transactional indicators  



## 🛠️ Tech Stack

| Category | Tools |
|---------|-------|
| Language | Python |
| Supervised ML | XGBoost |
| Deep Learning | LSTM Autoencoder (Keras / TensorFlow) |
| Libraries | pandas, numpy, scikit-learn, matplotlib |
| Environment | Jupyter Notebook |

---
