# Geochem Orebody Proximity Prediction

*Machine learning classification of geochemical drill assays to predict orebody proximity (proximal vs distal samples).*

---

## 📌 Project Overview
This project uses geochemical assay data from **Datarock’s Broken Down lead deposit (Tasmania)** to build a predictive model that classifies drill samples into two groups:  

- **Class A** → Proximal to the orebody  
- **Class B** → Distal from the orebody  

The aim is to automate orebody proximity classification for future drill holes using machine learning.

---

## 📊 Data Description
- **Total samples**: 4,472  
- **Features**: 8 geochemical elements (As, Au, Zn, Fe, S, Cu, Mo, Pb)  
- **Labels**: Class A (proximal), Class B (distal), and ~800 unlabeled samples (`?`)  
- **Additional metadata**: `uniqueID`, `holeid`, `from`, `to`  
- **Issues handled**: missing values, invalid values (`-999`, characters), detection limit inconsistencies  

---

## 🔄 Workflow
1. **QAQC & Cleaning**  
   - Handle missing values  
   - Remove invalid values (-999, non-numeric entries)  
   - Normalize / standardize assays  

2. **Exploratory Data Analysis (EDA)**  
   - Distribution plots for each element  
   - Correlation matrix  
   - PCA projection to visualize class separation  

3. **Model Training**  
   - Algorithms tested: Logistic Regression, Random Forest, XGBoost  
   - Cross-validation for performance metrics  

4. **Evaluation**  
   - Accuracy, Precision, Recall, F1-score  
   - Confusion matrix  
   - Feature importance (which elements contribute most to classification)  

5. **Prediction on Unlabeled Samples**  
   - Generate predicted labels for the `?` samples  
   - Export results for downstream use  

---

## 📈 Results
- **Best model:** Random Forest (placeholder – update once tested)  
- **Accuracy:** XX%  
- **Key features:** Fe, Pb, S (example – update with real importance plot)  

**Example outputs (to include once generated):**  
- Feature importance bar chart  
- Confusion matrix heatmap  
- PCA plot with predicted vs actual labels  

---

## 🚀 Usage
### 1. Clone the repo
```bash
git clone https://github.com/yourusername/geochem-orebody-proximity-prediction.git
cd geochem-orebody-proximity-prediction
