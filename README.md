[Colab Link](https://drive.google.com/file/d/1y_4p3i-18oIqDL3GMqcZiKkGiI0HyBqJ/view?usp=sharing)

# Predicting CO Levels with ARIMA, SARIMA, and LSTM Models

This project explores the prediction of carbon monoxide (CO) levels using various time series and machine learning models, including ARIMA, SARIMA, and LSTM. The dataset exhibits seasonal behavior, and the SARIMA model provides the best results among the classical methods.

---

## Dataset
The dataset contains measurements of air quality indicators, including CO levels, over a specific period. Key features include:
- PT08.S1(CO)
- C6H6(GT)
- PT08.S2(NMHC)
- NOx(GT)
- NO2(GT)
- PT08.S5(O3), etc.

---

## Model Results

### ARIMA Results
| Metric          | Value            |
|-----------------|------------------|
| Dependent Var.  | CO(GT)          |
| Observations    | 9351            |
| Model           | ARIMA(7, 1, 1)  |
| Log Likelihood  | -5212.973       |
| AIC             | 10453.945       |
| BIC             | 10553.949       |
| R² Score        | N/A             |

Significant coefficients:
- PT08.S1(CO): 0.0010 (p < 0.01)
- C6H6(GT): 0.1443 (p < 0.01)

### SARIMA Results
| Metric          | Value                   |
|-----------------|-------------------------|
| Dependent Var.  | CO(GT)                 |
| Observations    | 9351                   |
| Model           | SARIMAX(2, 1, 1)x(1, 1, 1, 24) |
| Log Likelihood  | -4375.178              |
| AIC             | 8776.356               |
| BIC             | 8869.183               |
| R² Score        | N/A                    |

Key Findings:
- SARIMA outperformed ARIMA in terms of lower AIC and BIC values.
- Seasonal behavior was well captured with SARIMA.

### LSTM Results
| Metric                     | Value          |
|----------------------------|----------------|
| Loss (Training)            | 0.0141        |
| Loss (Evaluation)          | 0.0136        |
| Mean Squared Error (MSE)   | 0.0136        |
| R² Score                   | 0.8130        |
| Optimizer                  | Adam          |
| Hyperparameters            | {'units_1': 50, 'units_2': 150} |

LSTM demonstrated strong predictive performance with an R² score of 0.813, indicating that 81.3% of the variance in CO levels is explained by the model.

### Random Forest Results
| Metric                     | Value          |
|----------------------------|----------------|
| Best Negative MSE          | -0.2163       |
| Accuracy                   | 84.14%        |

Random Forest achieved an accuracy of 84.14%, showcasing its capability in capturing non-linear relationships in the data.

---

## Conclusion
- SARIMA provided better results for the seasonal dataset compared to ARIMA.
- LSTM excelled in predictive power, capturing both linear and non-linear patterns.
- Random Forest achieved high accuracy, making it a viable alternative for time series forecasting.

---

## Future Improvements
- Incorporate additional features for further model enhancement.
- Experiment with hybrid models combining SARIMA and LSTM.
- Perform deeper hyperparameter tuning for Random Forest and LSTM.

---

## Dependencies
- Python
- TensorFlow/Keras
- Statsmodels
- Scikit-learn

---

## Author
Md. Fardin Khan

Feel free to explore and contribute to the project!
