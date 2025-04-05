# House Price Prediction

This project predicts median house values for California districts using the Scikit-learn California Housing dataset and a RandomForestRegressor model. It includes optional steps for Exploratory Data Analysis (EDA), geocoding-based feature engineering ('road', 'county'), and provides a simple manual input mechanism within the notebook for making predictions on new data.

## Features

*   Loads the California Housing dataset using Scikit-learn's `fetch_california_housing`.
*   **Optional EDA:** Generates an interactive Exploratory Data Analysis report using Sweetviz (if installed and enabled).
*   **Optional Geocoding:** Uses Geopy (if installed and enabled) to reverse geocode latitude/longitude coordinates, adding 'road' and 'county' features.
    *   Includes caching mechanism using `pickle` (`location_cache.pickle`) to avoid re-running the time-consuming geocoding process.
    *   Handles missing location data using mode imputation if geocoding is incomplete or skipped.
*   Encodes categorical features ('road', 'county', if added) using `LabelEncoder`. Saves the fitted encoders (`le_road_encoder.pkl`, `le_county_encoder.pkl`) using `pickle` for consistent transformation of new data.
*   Trains a `RandomForestRegressor` model on the processed features.
*   Evaluates the model's performance using the R² score on a held-out test set.
*   Provides a simple command-line style interface within the final cells of the notebook to manually input feature values and receive a house price prediction.

## Dataset

The project utilizes the **California Housing dataset** available through `sklearn.datasets.fetch_california_housing`.

*   **Features:** Median income, housing median age, average rooms, average bedrooms, population, average occupancy, latitude, longitude (Latitude and Longitude are dropped after optional geocoding).
*   **Target:** The median house value for California districts, expressed in hundreds of thousands of dollars ($100,000).

## Libraries Required

*   Python 
*   pandas
*   numpy
*   scikit-learn
*   matplotlib 
*   sweetviz (for EDA report)
*   geopy (for geocoding feature engineering)
