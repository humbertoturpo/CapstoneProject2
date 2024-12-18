# **Short-Term Forecasting of Monthly Fresh Ginger Exports from Peru Using Regression Models and Google Trends Indicators**

**Author**: Humberto Sebastian Turpo Huaman

---

## **Executive Summary**
This project predicts Peru's monthly ginger exports through short-term forecasting methods, combining lag-based regression with Google Trends data. By integrating search trends alongside traditional lagged exports, our models significantly improve forecast accuracy. The Lasso Regression model, adjusted for hyperparameters, notably outperformed others in terms of R-squared and error metrics.

---

## **Rationale**
As a leading ginger exporter, Peru must optimize its supply chain to meet global demands effectively. Traditional forecasting models, based only on historical data, miss rapid shifts in consumer interest and market conditions that modern data sources like Google Trends can highlight.

---

## **Research Question**
Can the inclusion of Google Trends indicators improve the accuracy of lag-based regression models for predicting Peru’s monthly ginger exports?

---

## **Data Sources**
1. **Export Data**: Monthly ginger export volumes sourced from official trade statistics.
2. **Google Trends Data**: Including Web, YouTube, Images, and News searches related to ginger, indexed from the month prior to each export record.

---

## **Methodology**
- **Models Deployed**: Linear Regression, Lasso, Ridge, ElasticNet, Random Forest, Gradient Boosting, XGBoost, and CatBoost.
- **Feature Importance**: Evaluated to identify the most influential predictors across models.
- **Hyperparameter Tuning**: Applied especially to models like Lasso, where it significantly impacted performance.
- **Evaluation Metrics**: R-squared, MSE, RMSE, MAE, and Explained Variance.

---

## **Key Results**
- **Best Performing Model**: XGBoost, with the highest R-squared (0.812834) and the lowest RMSE (861,877), indicating its superior accuracy and predictive power.
- **Feature Relevance**: Across models, `Exports12` (lagged exports), `Web`, and `YouTube` search indices proved most predictive of export volumes.
- **Visual Analysis**: Observations vs. Predicted plots and Residuals demonstrate that models integrating Google Trends data yielded more accurate and consistent predictions than the baseline model using only historical data.

---

## **Conclusion**
Incorporating Google Trends data with traditional forecasting models markedly enhances the prediction accuracy of ginger exports from Peru. Future work will explore deeper integration of digital behavior metrics and expand to more sophisticated models like neural networks to further enhance forecasting precision.

---

## **Appendix and Links**
- **Jupyter Notebook Analysis**: Detailed implementation and analysis are provided in the accompanying Jupyter notebook. [View Notebook](https://github.com/humbertoturpo/CapstoneProject1/blob/main/Capstone2.ipynb).

---

