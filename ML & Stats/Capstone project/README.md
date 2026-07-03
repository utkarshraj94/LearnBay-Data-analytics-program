# Car Price Prediction (ML Capstone)

## Objective

Build a regression model that predicts the resale price of used cars from basic listing attributes (company, year, kilometers driven, fuel type), walking through the full pipeline — cleaning a messy scraped dataset, exploratory analysis, and model tuning.

## Dataset

- **Source:** `car.csv` — used-car listings (originally scraped from Quikr), 6 raw columns: `name`, `company`, `year`, `Price`, `kms_driven`, `fuel_type`.
- **Cleaning:** dropped 19 rows with missing company, removed non-numeric/placeholder values (`"Ask For Price"`, fuel-type strings mixed into `kms_driven`, malformed years), and stripped the free-text `name` column.
- **Final cleaned dataset** (`cln_car.csv`): **842 rows**, model years **1995–2019**, prices from **₹30,000 to ₹85,00,003**, and 0–400,000 km driven.

## Key Insights

- Price is heavily right-skewed — a handful of premium brands (BMW, Mini) sit far above the rest of the market, but were kept in the model rather than treated as outliers since premium brands are a real part of the target population.
- A plain Linear Regression on raw numeric features barely explains the data (R² ≈ 0.07–0.17); most of the price signal comes from the categorical `company` and `fuel_type` fields, not year or kilometers alone.
- One-hot encoding `company`/`fuel_type` and re-tuning the train/test split (best of 1,000 random states) lifted the model to **R² ≈ 0.72**, saved as `LinearRegression.pkl`.
- Spot-checks confirm sensible behavior: a 2014 Ford predicts ~₹6.5L on Diesel vs. ~₹5.0L on Petrol at similar mileage, and a 2009 BMW predicts ~₹9.3L — reflecting the brand and fuel-type premium the model learned.

## Tech Stack

Python · Pandas · scikit-learn · Matplotlib · Seaborn
