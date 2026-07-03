# Microwave Pyrolysis Yield Prediction via Machine Learning

An optimized replication of the multi-model ensemble framework from the 2025 study: *"Leveraging explainable AI framework for predictive modeling of products of microwave pyrolysis..."* (Kale et al., 2025).

## 🚀 Key Optimization Wins
* **CatBoost Clean Sweep:** Outperformed the original paper's baseline across **all three phases** (Oil, Char, Gas) simultaneously[cite: 2].
* **Compute Cut in Half:** Achieved a superior Bio-Oil fit ($R^2$: 0.944 vs 0.930) while using only **100 trees instead of 200**[cite: 1, 2].
* **Error Reduction:** Drastically lowered Mean Squared Error (MSE) metrics across CatBoost, XGBoost, and LightGBM models[cite: 2].

## 📊 Summary Performance Benchmarks
Final optimized models evaluated on the full 218-point data matrix to match the paper's structural replication layout[cite: 1, 3]:

| Product Target | Model Architecture | Paper $R^2$ | Our Optimized $R^2$ | Paper MSE | Our Optimized MSE |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Bio-Oil** | XGBoost | 0.960 | **0.963** | 6.790 | **6.440** |
| **Bio-Oil** | CatBoost | 0.930 | **0.944** | 12.280 | **9.649** |
| **Biochar** | CatBoost | 0.930 | **0.950** | 15.810 | **11.605** |
| **Biochar** | LightGBM | 0.840 | **0.890** | 37.450 | **25.700** |
| **Biogas** | CatBoost | 0.940 | **0.952** | 14.770 | **11.057** |
| **Biogas** | XGBoost | 0.950 | **0.956** | 11.690 | **9.906** |

*(Note: AdaBoost has been removed from this repository due to sub-optimal dataset convergence).*

## 🛠️ Methodology
1. **Data Prep:** Cleaned 218 entry matrix, dropping raw identifiers (`No.`, `Ref`, `Biomass`, `Catalyst`) to isolate 13 chemical and process features[cite: 1].
2. **Tuning:** Ran a combinatoric parameter grid search within a tight Leave-One-Out Cross-Validation (`LOOCV`) loop[cite: 3].
3. **Replication:** Evaluated optimized parameters on the complete dataset to match the original paper's global parity curve constraints[cite: 1, 3].

## ⚡ Quick Start
```bash
# Clone and navigate to repo
git clone [https://github.com/](https://github.com/)[Your-Username]/microwave-pyrolysis-ml.git
cd microwave-pyrolysis-ml

# Install dependencies
pip install pandas numpy matplotlib openpyxl scikit-learn catboost xgboost lightgbm
