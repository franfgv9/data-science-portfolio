# Probabilistic AI: Football Match Forecasting & Utility Analysis

## Project Overview
This project develops a probabilistic forecasting system for Portuguese football league matches, applying Bayesian Networks, uncertainty quantification, and utility theory to analyse the sports betting market. Instead of merely predicting the winning team, the focus is on estimating reliable probabilities, understanding the model's confidence, and making decisions by comparing these probabilities with market odds.

## Main Objectives
* **Bayesian Networks:** Construct and evaluate Bayesian Networks using both Knowledge Engineering (manual) and automatic structure learning (Hill Climbing with BIC/BDeu) to understand variable dependencies.
* **Parameter Learning:** Compare Maximum Likelihood Estimation (MLE) and Bayesian Estimation (BDeu prior) to avoid zero-probability errors in rare configurations.
* **Uncertainty & Calibration:** Train a Naive Bayes classifier, apply Split Conformal Prediction for valid prediction sets, and calibrate probabilities using Platt Scaling (evaluating via Brier Score, Log Loss, and ECE).
* **Decision Making & Utility:** Compare calibrated probabilities against betting odds to identify "value bets" and implement a "Reject Option" strategy, deferring to the market or abstaining when the model is highly uncertain.

## Technologies & Tools
* **Language:** Python
* **Probabilistic Modeling:** `pgmpy` (Discrete Bayesian Networks, Inference, Hill Climbing)
* **Machine Learning & Calibration:** `scikit-learn` (Naive Bayes, Platt Scaling, Brier Score, Log Loss)
* **Hyperparameter Optimization:** `scikit-optimize` (Bayesian Optimization)
* **Data Manipulation & Visualization:** `pandas`, `numpy`, `matplotlib`, `graphviz`

## Key Insights & Conclusions
* **Structure Learning vs. Domain Knowledge:** While automatic learning (BIC) found some logical connections, the manually designed Bayesian Network proved more interpretable and conceptually sound for the football domain.
* **Calibration Matters:** The uncalibrated Naive Bayes model produced overconfident probabilities. Applying Platt Scaling significantly reduced the Log Loss (from 1.145 to 0.955) and the Expected Calibration Error (ECE from 0.124 to 0.034).
* **Handling Uncertainty:** Split Conformal Prediction achieved the target 90% coverage, but the prediction sets were often large, highlighting the inherent noise in football forecasting (especially for the "Draw" class).
* **The "Reject Option" Value:** A hybrid decision strategy combining model confidence, strict value bets ($EV > 0.15$), and deferral to odds improved decision-making. Simply predicting every match yielded 55% accuracy, whereas applying a confidence-based Reject Option improved accuracy to 68% on the accepted matches.