### Modeling (Feasibility)

The QAQC and EDA confirmed that the geochemical assay dataset can be cleaned and structured for analysis.  
However, on its own the dataset is **not sufficient** for robust predictive modeling.  
The dataset needs to be **enriched with additional features** and **guided by domain expertise** before predictive models can be applied with confidence.  
Further work is required to integrate geological context, spatial information, and larger labeled datasets to improve feasibility.


---

## 📈 Findings (from QAQC + EDA)
- **Log transform is essential** (skew reduction, clearer patterns).  
- Strong signals from **Cu, Zn, Pb, Mo**, with Fe and S providing context.  
- **As** retained (31% missing) with flags; **Au** often near detection limit.  
- **Imbalance** will bias naive models → use class weights or resampling.

---

## 🧪 Reproducible Outputs
- `cleaned_data.csv`  
- `cleaned_data_for_ML.csv`  
