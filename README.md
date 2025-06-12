🚕 Airport Taxis – Time Series Prediction
📍 Project Overview
Sweet Lift Taxi has collected historical data on taxi orders at airports. To better allocate drivers during peak hours, the company wants to predict the number of taxi orders for the next hour. We built a time series forecasting model with the business constraint that the RMSE on the test set must not exceed 48.

🎯 Objective
Predict the number of taxi orders for the upcoming hour using historical time-series data.

Resample the data to hourly intervals and build predictive models.

Tune and compare different machine learning approaches.

Ensure the final model achieves RMSE ≤ 48 on the test data.

---

- **Python**
- **Pandas** – for data manipulation
- **NumPy** – for numerical operations
- **Matplotlib & Seaborn** – for data visualization
- **Scikit-learn** – for machine learning models (lightGBM, Linear Regression)

---

🧹 Preprocessing
Converted the index to a datetime format and resampled by 1 hour.

Verified that there were no duplicates or missing values.

Engineered time-based features (e.g., hour of day, day of week).

Ensured all features were in the correct format before model training.

🤖 Model Training & Evaluation
Model	Train RMSE	Test RMSE	Notes
Linear Regression	Baseline	>48	For comparison
AutoRegression	~55	~55	Did not meet target
Dummy Regressor	—	49	Baseline model
LightGBM	30	12	Best performer
Random Forest	29	16	Strong, but slightly less accurate than LightGBM

✅ Both LightGBM and Random Forest models beat the 48 RMSE threshold, with LightGBM being the most consistent and accurate on unseen test data.

📌 Conclusion
The final LightGBM model significantly exceeds expectations, delivering:

Train RMSE: 30

Test RMSE: 12 (well below the required threshold of 48)

This model gives Sweet Lift Taxi a reliable way to predict hourly taxi demand and helps optimize driver availability during peak times.
