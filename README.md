# Heart Disease Prediction - Data Mining Course Project

**Course:** Data Mining

---

## Overview
This project involves predicting heart disease using two datasets obtained from Kaggle. Both datasets contain identical columns, representing results from the same study, with one dataset being an extended version of the other. We merged the datasets and removed duplicates.

The combined dataset includes the following columns:

| Column | Description |
|--------|-------------|
| Age | Patient's age |
| sex Patient's gender |
| Cp | CP level of the patient
| Trestbps | Resting blood pressure |
| Chol | Cholesterol level
| Facebook | Fasting blood sugar |
| Restecg | Resting ECG results |
| Thalach | Maximum heart rate achieved
| Exang | Exercise induced angina
| Oldpeak | Old Peak History Recorded |
| Slope | Slope of peak exercise ST segment |
| Ca| Number of major vessels colored by fluoroscopy
| Thal | Thalassemia (blood disorder) |
| Target | Prediction column: 0 – Healthy, 1 – Heart disease

The dataset in Excel format is included in the repository.

---

## Experiments and Preprocessing

### Experiment Runs

1. **Run 1:** Removed `slope` due to high correlation with `oldpeak`. Applied binning with 100 bins.
2. **Run 2:** Same as Run 1, but removed `oldpeak` instead. Results were almost identical.
3. **Run 3:** Same as Run 2, but used 3 bins. Results remained similar except for K-Means.
4. **Run 4:** Same as Run 2, but used 150 bins. Results similar to Run 2. 
- **Conclusion:** Number of bins did not significantly affect results.

5. **Run 5:** Removed `slope` and `oldpeak`. Decimal scaling applied to `thalach`.
6. **Run 6:** Removed `slope` and `oldpeak`. Decimal scaling applied to `age`, `chol`, `fbs`.
7. **Run 7:** Z-score normalization applied to `age`, `chol`. Decimal scaling for `trestbps`.
8. **Run 8:** No preprocessing applied.
9. **Run 9:** Z-score normalization applied to `age`, `chol`, `thalach`, `trestbps`. Decimal scaling applied to `fbs`, `ca`. ✅ Best results.
10. **Run 10:** Binning applied to `thalach` and `trestbps` using mean and 50 bins.
11. **Run 11:** Removed `oldpeak`. Min-Max scaling applied to `chol` and `slope`. Normalized `resteg`, `sex`, `ca`, `cp`.

---

### Notes
- Run 9 gave the best performance, likely because z-score normalization was applied to columns with large numeric ranges.
- The best-performing model across experiments was **Naive Bayes**.

---

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-Learn

---

## How to Use
1. Load the dataset (`.xlsx`) included in the repository.
2. Run the preprocessing and modeling scripts to replicate experiments.
3. Analyze results to compare different preprocessing strategies.

---

## License
This project is for educational purposes.
