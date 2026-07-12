# Model Definition and Evaluation

**[Notebook](model_definition_evaluation)**

## Overview

This project develops a neural network to predict the final score of a Hanabi game based on the cards currently held by both players. The workflow consists of data preprocessing, feature engineering, hyperparameter optimization, model training, and evaluation.

## Data Preprocessing

Before training, the dataset was split into training, validation, and test sets. All input features were normalized using **Min-Max Scaling**. The scaler was fitted only on the training data and then applied to the validation and test sets to prevent data leakage.

## Feature Engineering

Several additional features were created to provide the model with more informative representations of the game state:

- **Card value counts:** Total number of cards with values 1–5 across both players.
- **Color counts:** Total number of cards of each color across both players.
- **Player hand statistics:** Sum and average value of each player's hand.
- **Unique cards:** Number of distinct cards held by each player.
- **Average maximum possible progress:** A feature estimating how far each color stack could potentially be progressed based on the cards currently available in both players' hands.

These engineered features complement the original card representation and provide higher-level information about the game state.

## Hyperparameter Optimization

Hyperparameter tuning was performed using **Optuna** with the **Tree-structured Parzen Estimator (TPE)** sampler. A total of **500 trials** explored different combinations of:

- Number of hidden layers
- Hidden layer size
- Dropout rate
- Learning rate
- Weight decay
- Batch size

The best configuration was selected based on the lowest validation **Mean Squared Error (MSE)**.

## Final Model

The final model is a fully connected feedforward neural network implemented in PyTorch. Its architecture is dynamically constructed using the optimal hyperparameters found by Optuna. Hidden layers consist of:

- Linear layers
- ReLU activation functions
- Dropout for regularization

The network was trained using the **Adam optimizer** and **Mean Squared Error (MSE)** loss.

To improve generalization and training stability, the training procedure also included:

- **Early stopping** to prevent overfitting.
- **ReduceLROnPlateau** learning rate scheduling to reduce the learning rate when validation performance stopped improving.

The model with the lowest validation loss was saved and restored before the final evaluation.

## Evaluation

Model performance was evaluated on the unseen test set using several regression metrics:

- **Mean Squared Error (MSE):** Measures the average squared prediction error.
- **Root Mean Squared Error (RMSE):** Expresses the prediction error in the same units as the target variable.
- **Mean Absolute Error (MAE):** Measures the average absolute prediction error.
- **R² Score:** Indicates how well the model explains the variance in the target values.

Together, these metrics provide a comprehensive assessment of the model's predictive performance.