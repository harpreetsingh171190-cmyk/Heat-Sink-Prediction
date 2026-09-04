# Heat Sink Thermal Performance Prediction using Machine Learning

## Overview
This project applies machine learning techniques to predict the thermal dissipation performance of finned heat sinks used in electronics cooling. By bridging mechanical engineering heat transfer principles with predictive data modeling, this script evaluates how geometric parameters and airflow affect the overall heat transfer rate ($Q$) and thermal resistance ($R_{th}$).

## Features
* **Physics-Based Data Generation:** Automatically synthesizes a robust dataset of 2,000 unique heat sink designs using empirical convective heat transfer equations.
* **Exploratory Data Analysis (EDA):** Generates correlation matrices and distribution plots to identify primary drivers of thermal efficiency.
* **Multi-Model Regression:** Evaluates and compares three machine learning algorithms to find the most accurate predictive model:
  * Linear Regression
  * Random Forest Regressor
  * Gradient Boosting Regressor (Achieved peak accuracy: ~94.8% $R^2$)
* **Custom Inference Engine:** Includes a standalone function to input new, custom heat sink dimensions and instantly predict cooling performance without running a full CFD simulation.

## Tech Stack
* **Language:** Python 3
* **Data Manipulation:** NumPy, Pandas
* **Machine Learning:** Scikit-Learn
* **Data Visualization:** Matplotlib, Seaborn

## Methodology
The dataset relies on standard convective cooling formulas where the heat transfer coefficient ($h$) is a function of air velocity and fin geometry. The model predicts the Heat Transfer Rate ($Q$, in Watts) and Thermal Resistance ($R_{th}$, in °C/W) based on the following inputs:
* Fin Length, Thickness, Height, and Pitch (m)
* Air Velocity (m/s)
* Temperature Difference ($\Delta T$ in °C)

## Usage
1. Clone the repository.
2. Ensure you have the required libraries installed (`pip install numpy pandas scikit-learn matplotlib seaborn`).
3. Run the Jupyter Notebook or Python script to generate the dataset, train the models, and view the visual analysis (Parity Plot, Feature Importance, Residuals).
4. Use the `predict_heat_sink()` function at the end of the script to test your own custom designs.
