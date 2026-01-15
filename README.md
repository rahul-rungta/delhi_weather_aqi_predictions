# delhi_weather_aqi
AQI Prediction & Air Quality Analysis (Delhi)
Project Overview
Air pollution is a critical environmental and public health issue in major Indian cities like Delhi.
This project analyzes meteorological and pollutant factors affecting the Air Quality Index (AQI) and builds a machine learning model to accurately predict AQI levels.

The project follows an end-to-end analytics pipeline:
Exploratory Data Analysis (EDA)
Statistical hypothesis testing
Feature selection
Machine learning modeling
Model interpretation

Objectives
Identify key variables influencing AQI
Apply appropriate statistical tests based on data distribution
Build and evaluate predictive models for AQI
Interpret feature importance using domain knowledge

Dataset
Delhi Weather & AQI Dataset
Key Variables:
Meteorological: temperature, humidity, pressure, wind speed
Pollutants: PM2.5, PM10, CO, NO₂
Target: AQI Index
Categorical: weather condition (condition_text)

Exploratory Data Analysis (EDA)
Visualized distributions of all numeric variables
Identified strong skewness in pollutant variables (PM2.5, PM10, CO, NO₂)
Dropped latitude & longitude due to lack of spatial variation
Converted continuous variables into quantile-based bins for analysis

Statistical Hypothesis Testing
Different tests were selected based on distribution and variable type:
Variable	Test Used	Result
Temperature	One-way ANOVA	Significant
Humidity	One-way ANOVA	Significant
Pressure	Kruskal–Wallis	Significant
Wind Speed	Kruskal–Wallis	Significant
PM2.5	Kruskal–Wallis	Highly significant
PM10	Kruskal–Wallis	Highly significant
CO	Kruskal–Wallis	Significant
NO₂	Kruskal–Wallis	Significant
Weather Condition	Chi-Square Test	Significant

All tests were conducted at α = 0.05
Machine Learning Models

Baseline Model – Linear Regression
MAE ≈ 93
R² ≈ 0.70
Limited performance due to non-linear and threshold-based AQI formulation.

Final Model – Random Forest Regressor
MAE ≈ 49
R² ≈ 0.89
Captured non-linear relationships
Significantly improved prediction accuracy

Feature Importance (Random Forest)
Feature	Importance
PM10	0.75
PM2.5	0.05
Temperature	0.04
Humidity	0.04
NO₂	0.04
CO	0.03
Wind Speed	0.03
Pressure	0.02
Key Insight:
PM10 emerged as the dominant predictor
PM2.5 and PM10 show moderate correlation (ρ ≈ 0.67)
Random Forest prioritized PM10 due to higher variance and stronger split efficiency during high-AQI events

Key Insights
AQI is primarily driven by particulate matter (PM10 & PM2.5)
Meteorological factors influence AQI indirectly
Tree-based models outperform linear models for AQI prediction
Feature importance aligns with real-world pollution dynamics

Conclusion
This project demonstrates a rigorous, data-driven approach to understanding and predicting air quality.
By combining statistical testing with machine learning, it provides both explainability and predictive power, making it suitable for real-world environmental analytics.

Tools & Technologies
Python
Pandas, NumPy
Matplotlib, Seaborn
SciPy (ANOVA, Kruskal–Wallis, Chi-Square)
Scikit-learn (ML models)

Future Enhancements
SHAP-based model explainability
AQI category classification
Time-series forecasting
Interactive dashboard (Tableau / Power BI)


Author
Rahul Rungta
Data Analyst | Machine Learning Enthusiast
