# CodeAlpha_CAR_PREDICTION_INTERNSHIP
# 🚗 Car Price Prediction Using Machine Learning

## Project Overview

This project uses machine learning regression techniques to estimate the
selling price of a used car based on its available features. It covers
data cleaning, exploratory data analysis (EDA), feature engineering,
preprocessing, model training, evaluation, and a Streamlit application
for making predictions.

The predicted price is an estimate, not a guaranteed market value.

## Objectives

-   Clean and understand used-car data.
-   Explore relationships between car features and selling price.
-   Prepare numerical and categorical data for machine learning.
-   Train and compare regression models.
-   Evaluate model performance.
-   Save the trained model and use it in a Streamlit application.

## Technologies and Libraries

-   Python
-   Pandas and NumPy
-   Matplotlib
-   Scikit-learn
-   Joblib
-   Streamlit
-   Jupyter Notebook / Anaconda

## Dataset

The notebook is designed for a `car data.csv` dataset in the common
CarDekho format.

Typical columns include:

  Column            Description
  ----------------- ------------------------------------------------------------
  `Selling_Price`   Selling price of the car (prediction target)
  `Present_Price`   Current ex-showroom price
  `Driven_kms`      Distance driven by the car
  `Fuel_Type`       Fuel type
  `Selling_type`    Dealer or Individual
  `Transmission`    Manual or Automatic
  `Owner`           Number of previous owners
  `Year`            Year of manufacture; converted to `Car_Age` when available

The notebook uses columns that actually exist in the CSV; it does not
assume missing features.

## Project Workflow

1.  Load the CSV dataset using Pandas.
2.  Inspect column names, data types, summary statistics, and missing
    values.
3.  Clean text values, remove duplicate rows, and handle invalid target
    values.
4.  Perform EDA using price distributions, feature relationships,
    categorical comparisons, and correlations.
5.  Convert `Year` into `Car_Age` when the year column is available.
6.  Preprocess numerical features using median imputation and standard
    scaling.
7.  Preprocess categorical features using most-frequent imputation and
    one-hot encoding.
8.  Split the data into training and testing sets (80% / 20%).
9.  Train and compare Linear Regression, Random Forest Regressor, and
    Extra Trees Regressor.
10. Evaluate models using MAE, RMSE, and R² score. The notebook selects
    the model with the lowest RMSE.
11. Save the trained preprocessing-and-model pipeline with Joblib.
12. Use the saved model in a Streamlit application to estimate a car's
    selling price.

## Project Files

Keep the following files in the same project folder:

``` text
CAR_PREDICTION_INTERNSHIP/
├── app.py
├── car data.csv
├── car_price_prediction_model.pkl
├── Car_Price_Prediction_Edited.ipynb
└── README.md
```

If your actual notebook or saved-model filename is different, update the
filename in the app or this file.

## Installation

### 1. Create and activate a virtual environment (Windows)

The saved model was created with scikit-learn 1.6.1. Use a compatible
environment when loading it.

``` bash
py -3.12 -m venv carenv
carenv\Scripts\activate
```

### 2. Install the required packages

``` bash
python -m pip install --upgrade pip
python -m pip install scikit-learn==1.6.1
python -m pip install streamlit pandas numpy joblib matplotlib
```

## Run the Streamlit Application

Open Command Prompt in the project folder, activate the environment, and
run:

``` bash
carenv\Scripts\activate
python -m streamlit run app.py
```

Open the local address printed in the terminal, usually
`http://localhost:8501`.

If you open a new Command Prompt window, activate `carenv` again before
starting the app. The model may not load correctly if a different
scikit-learn version is used.

## Model Evaluation

-   **MAE (Mean Absolute Error):** average absolute difference between
    actual and predicted prices. Lower is better.
-   **RMSE (Root Mean Squared Error):** gives more weight to larger
    prediction errors. Lower is better.
-   **R² Score:** indicates how much variation in the target is
    explained by the model. A value closer to 1 is generally better.

Refer to the completed notebook output for the actual scores; no
performance values are assumed in this README.

## Expected Outcome

The Streamlit application accepts car details and returns an estimated
selling price from the trained regression pipeline.

## Limitations

-   Prediction quality depends on the size, quality, and
    representativeness of the training dataset.
-   The model can only learn from features included in the dataset.
-   Vehicle condition, accident history, service records, location, and
    current market demand may not be represented.
-   The prediction is an estimate, not a guaranteed selling price.
-   Validate the model with recent data before using it for commercial
    decisions.

## Future Improvements

-   Add more recent and geographically diverse used-car data.
-   Include reliable vehicle-condition and service-history features, if
    available.
-   Tune model hyperparameters and use cross-validation.
-   Improve the Streamlit interface with clearer input guidance and
    visual summaries.
-   Monitor prediction performance as market prices change.

------------------------------------------------------------------------

*This project is developed for learning and demonstrating a
machine-learning regression workflow.*

#Run Command
carenv\Scripts\activate
python -m streamlit run app.py
