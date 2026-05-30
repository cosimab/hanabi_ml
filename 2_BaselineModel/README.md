# Baseline Model

**[Notebook](baseline_model.ipynb)**

## Baseline Model Results

### Model Selection
- **Baseline Model Type:** Linear Regression
- **Rationale:** We chose linear regression as a baseline model because we have a continuous numerical target variable (the final score) that we want to predict.

### Model Performance
- **Evaluation Metric:** RMSE
- **Performance Score:** RMSE of 5.7106
- **Cross-Validation Score:** RMSE of 5.7296 ± 0.0540

### Evaluation Methodology
- **Data Split:** Train/Test split 80/20
- **Evaluation Metrics:** We're using MSE/RMSE as our evaluation metric because it's the standard metric for evaluating regression models.

### Metric Practical Relevance
A lower RMSE stands for a better prediction of the final score of the game. More accurate score predictions can help evaluate the strength of starting hands, improve game balancing, support strategy recommendations and provide players with better insights into likely outcomes.

## Next Steps
This baseline model serves as a reference point for evaluating more sophisticated models in the [Model Definition and Evaluation](../3_Model/README.md) phase.
