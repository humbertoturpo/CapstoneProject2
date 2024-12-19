# **Short-Term Forecasting of Monthly Fresh Ginger Exports from Peru Using Regression Models and Google Trends Indicators**

**Author**: Humberto Sebastian Turpo Huaman

---

## **Executive Summary**
This project predicts Peru's monthly ginger exports through short-term forecasting methods, combining lag-based regression with Google Trends data. By integrating search trends alongside traditional lagged exports, our models significantly improve forecast accuracy. The XGBoost model with Web Search Data, adjusted for hyperparameters, notably outperformed others in terms of R-squared and error metrics.

---

## **Rationale**
As a leading ginger exporter, Peru must optimize its supply chain to meet global demands effectively. Traditional forecasting models, based only on historical data, miss rapid shifts in consumer interest and market conditions that modern data sources like Google Trends can highlight. It is essential to incorporate variables that are immediately available, such as Google Trends data, as other critical data like price and inflation figures are often published with a delay of several months. Integrating these timely data sources significantly enhances the accuracy and responsiveness of our forecasting models, providing a more adaptive approach to predicting market trends and making informed decisions.

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

| Metrics                | Linear Regression | Lasso              | Ridge              | ElasticNet         | Random Forest      | Gradient Boosting  | XGBoost            | CatBoost           |
|------------------------|-------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|--------------------|
| R-squared              | 0.783702          | 0.783762           | 0.788310           | 0.789092           | 0.730479           | 0.778954           | 0.812834           | 0.772750           |
| Adjusted R-squared     | 0.744375          | 0.744446           | 0.749821           | 0.750745           | 0.666307           | 0.750121           | 0.797237           | 0.731432           |
| MSE                    | 8.584522e+11      | 8.582131e+11       | 8.401653e+11       | 8.370608e+11       | 1.069687e+12       | 8.772988e+11       | 7.428315e+11       | 9.019185e+11       |
| RMSE                   | 9.265270e+05      | 9.263979e+05       | 9.166053e+05       | 9.149103e+05       | 1.034257e+06       | 9.366423e+05       | 8.618768e+05       | 9.496939e+05       |
| MAE                    | 730567.284        | 730463.362         | 719015.584         | 717685.110         | 711209.146         | 775524.042         | 699269.840         | 668807.548         |
| Explained Variance     | 0.785636          | 0.785699           | 0.790793           | 0.791701           | 0.742740           | 0.782565           | 0.820288           | 0.778505           |
| Best Hyperparameters   | None              | {'alpha': 100.0}   | {'alpha': 2.559547922699533} | {'alpha': 0.29763514416313164, 'l1_ratio': 0.9} | {'max_depth': 20, 'min_samples_split': 2} | {'learning_rate': 0.01, 'max_depth': 5, 'n_estimators': 200} | {'learning_rate': 0.01, 'max_depth': 3, 'n_estimators': 300} | {'depth': 6, 'iterations': 1000, 'learning_rate': 0.03} |
| Features Included      | Exports12, Web, Images, News | Exports12, Web, Images, News | Exports12, Web, Images, News | Exports12, Web, Images, News | Exports12, YouTube, Web, News, Images | Exports12, Web, YouTube | Exports12, Web, YouTube | Exports12, YouTube, Web, News |





- **Best Performing Model**: XGBoost, with the highest R-squared (0.812834) and the lowest RMSE (861,877), indicating its superior accuracy and predictive power.
- **Feature Relevance**: Across models, `Exports12` (lagged exports), `Web`, and `YouTube` search indices proved most predictive of export volumes.
- **Visual Analysis**: Observations vs. Predicted plots and Residuals demonstrate that models integrating Google Trends data yielded more accurate and consistent predictions than the baseline model using only historical data.

---

## **Conclusion**
Incorporating Google Trends data with traditional forecasting models markedly enhances the prediction accuracy of ginger exports from Peru. Future work will explore deeper integration of digital behavior metrics and expand to more sophisticated models like neural networks to further enhance forecasting precision.

---


## **Next Steps**
1. **Implement Model**: Run the XG Boost model at the beginning of each month, for example, to determine Peruvian ginger exports for June 2026, the model could be run in the first minutes of June 1st.
2. **Future Directions**: Explore sentiment analysis to gauge the emotional tone of search-related data and continually monitor and update the model to adapt to new trends. Employ computer vision to extract additional insights from visual data for enhanced marketing strategies.

---

## **Outline of Project**
[Dataset](https://github.com/humbertoturpo/CapstoneProject2/tree/main/data)

[Notebook](https://github.com/humbertoturpo/CapstoneProject2/blob/main/CapstoneGinger.ipynb)






## **Contact and Further Information**
**Humberto Sebastian Turpo Huaman**  
[sebastian.turpo@gmail.com]  

---
