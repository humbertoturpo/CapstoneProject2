# **Short-Term Forecasting of Monthly Fresh Ginger Exports from Peru Using Regression Models and Google Trends Indicators**

**Author**: Humberto Sebastian Turpo Huaman

---

## **Executive Summary**
This project predicts Peru's monthly ginger exports through short-term forecasting methods, combining lag-based regression with Google Trends data. By integrating search trends alongside traditional lagged exports, our models significantly improve forecast accuracy. The XGBoost model, adjusted for hyperparameters, notably outperformed others in terms of R-squared and error metrics.

---

## **Rationale**
As a leading ginger exporter, Peru must optimize its supply chain to meet global demands effectively. Traditional forecasting models, based only on historical data, miss rapid shifts in consumer interest and market conditions that modern data sources like Google Trends can highlight.

---

## **Research Question**
Can the inclusion of Google Trends indicators improve the accuracy of lag-based regression models for predicting Peru’s monthly ginger exports?

---

## **Data Sources**
1. **Export Data**: Monthly export volumes sourced from TradeMap.  
2. **Google Trends Indicators**: Search interest data (Web, YouTube, Image, and News searches) retrieved from Google Trends.
   - **Temporal Alignment**: Search data corresponds to the month prior to the export period, ensuring alignment with lagged market behavior.

- **Exports**: Represents the monthly ginger export volumes from Peru.
- **Exports12**: Refers to lagged data of export volumes, specifically a 12-month lag.
- **Web**: Indicates lagged search interest data from general web searches associated with food and beverage topics, representing the previous month.
- **YouTube**: Refers to lagged search interest data from YouTube, capturing food and beverage-related trends from the prior month.
- **Images**: Represents lagged search interest data from image-based searches related to food and beverage, conducted a month earlier.
- **News**: Refers to lagged search interest data from news-related searches about food and beverage, reflecting public interest from the previous month.


- The **Exports** tag provides the primary dependent variable for forecasting.
- All other tags (Exports12, Web, YouTube, Images, News) are lagged variables, capturing trends from one month prior. These lagged indices specifically track online searches related to food and beverage topics, enabling predictive modeling by aligning consumer search behavior with subsequent export activities.


   | Feature             | Unit       |
   |---------------------|------------|
   | Exports             | kg         |
   | Exports12           | kg         |
   | Search Indices      | Unitless   |


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


## **Next Steps**
1. **Neural Networks**: Explore advanced architectures, such as recurrent neural networks (RNNs) or long short-term memory (LSTM) networks, to model non-linear relationships.  
2. **Dataset Expansion**: Apply Gaussian noise to augment the dataset, creating diverse scenarios for better generalization and robustness.  
3. **Model Optimization**: Focus on hyperparameter tuning for both regression and neural network models to maximize performance.

---

## **Outline of Project**
[Dataset](https://github.com/humbertoturpo/CapstoneProject1/blob/main/data/gingerperu2.xlsx)

[Notebook](https://github.com/humbertoturpo/CapstoneProject2/blob/main/CapstoneGinger.ipynb)


