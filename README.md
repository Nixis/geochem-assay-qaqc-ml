# Geochem Dataset QAQC for Machine Learning

*Quality control and exploration of a geochemical dataset to test its feasibility for predictive modeling.*

---

## 📌 Project Goals
1) **QAQC the dataset** (legacy + new assays) to ensure it’s clean, consistent, and traceable.  
2) **Establish feasibility**: Can these assays + labels train a predictive model for future drill holes (Class **A** vs **B**)?  
3) **Future step**: Once models are validated, apply them to the **unlabeled** samples (“**?**”) and export predictions for geological review.

**Classes**  
- **A** → Proximal (higher mineralization potential)  
- **B** → Distal (lower mineralization potential)  
- **?** → Unlabeled (to be predicted in future work)

---

## 📊 Data Summary
- **Samples**: ~4,771  
- **Assays (8)**: As, Au, Pb, Fe, Mo, Cu, S, Zn  
- **Labels**: A, B, ?  
- **Metadata**: `Unique_ID`, `holeid`, `from`, `to`

**Common data issues handled**
- Missing values (notably **As ~31%**)  
- Truncated values at detection limits (e.g., “`<0.005`”)  
- Invalid placeholders (e.g., **-999**)  
- Skewed distributions across assays

---

## 🔄 Workflow

### QAQC & Cleaning
- Replace invalid placeholders with `NaN` and **flag**.  
- Parse **truncated** values (“`<DL`”) → numeric + **trunc_flag**.  
- Missing/truncated rules (per element):
  - **<10%** → substitute (DL/√2 or median)
  - **10–40%** → substitute **and** keep flags
  - **>40%** → recommend **exclusion** from ML  
- Outputs:
  - `cleaned_data.csv` → raw + clean + flags (traceable)  
  - `cleaned_data_for_ML.csv` → compact ML-ready (metadata + *_clean + *_flag)

### Exploratory Data Analysis (EDA)
- **Distributions**: raw values are highly skewed → use **log scale** for modeling/plots.  
- **Class balance**: A (~60%), B (~24%), ? (~16%) → **imbalance** needs handling.  
- **Relationships**: strong pairs (e.g., **Cu–Zn**, **Mo–Pb**); many others weak/moderate.  
- **PCA**: PC1+PC2 ≈ **~52%** variance; partial A/B separation with overlap.

---

## 🤔 Project Feasibility

The QAQC and EDA confirmed that the geochemical assay dataset can be cleaned and structured for analysis.  
⚠️ However, the dataset alone is **not sufficient** for robust predictive modeling.  

To move forward:  
- Enrich with **geological context** and **spatial data**  
- Incorporate **expert domain knowledge**  
- Expand the labeled dataset (reduce class imbalance)  
- Validate predictive models with robust cross-validation  

**Conclusion:** More data and expert integration are required before reliable predictive models can be deployed.

---

## 📈 Current Findings (from QAQC + EDA)
- **Log transform is essential** (skew reduction, clearer patterns).  
- Strong signals from **Cu, Zn, Pb, Mo**, with Fe and S providing context.  
- **As** retained (31% missing) with flags; **Au** often near detection limit.  
- **Imbalance** will bias naive models → use class weights or resampling.

---

## 🧪 Reproducible Outputs
- `cleaned_data.csv`  
- `cleaned_data_for_ML.csv`  

---

## 🙏 Acknowledgments
This project makes use of geochemical assay data kindly provided by **Datarock**.  
Their dataset enabled the exploration and demonstration of machine learning workflows in geoscience.  
Special thanks to Datarock for supporting open, practical applications of data science in the mining and exploration industry.  

**Citation:**  
Dataset © Datarock, 2025. Broken Down Lead Deposit (Tasmania) geochemical assays.  
Used with permission for educational and research purposes.  
