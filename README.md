# 🛒 Basket Size Prediction

This project was developed as part of a data science case study to estimate the **basket size** of customers in a real-world e-commerce grocery platform. Using event-level behavioral data and product metadata, we trained a predictive model to accurately forecast the number of items users would purchase in a session.

---

## 🎯 Objective

Predict the **basket size** (number of products purchased) based on user interaction patterns and session-level features. The aim is to support inventory management and personalized user recommendations by anticipating purchase volumes.

---

## Contents of the Case Study

### Dataroid_Research.py 

- This file includes all the model development steps and research done to obtaib the optimal model and methods.

### Dataroid__Pipeline.py 

- This file includes the whole pipeline to produce the final model with the best hyperparameters. 

- It only contains necessary steps studied in the research file.

- Instruction are below about how to run.

### Datariod_EDA.ipynb

- This file includes all the notes about the exploratory data analysis process.

- The outline of the results of EDA are below.

---

## 📊 Dataset Description

The dataset contains user event logs from a grocery-focused e-commerce platform. Event types include:

- `ViewProduct`
- `AddToCart`
- `RemoveFromCart`
- `AddToWishlist`
- `RemoveFromWishlist`
- `Purchase`
- `ClearCart`

### Key Feature Types

**🧮 Numerical Features:**
- Product price
- Product quantity
- Cart and wishlist metrics
- View and purchase counts
- Time since last purchase
- Basket total value

**🏷️ Categorical Features:**
- Brand
- Category
- Product name
- Device info
- Day, Hour
- Weekend indicator

---

## 🧪 Modeling

The best results were obtained using the **CatBoost Regressor**, which handles categorical features efficiently and performs well on tabular data with mixed types.

- Feature engineering focused on aggregating event-level interactions at the session/user level.
- Data was split into training and test sets using time-based validation.

---

## ✅ Results

| Metric | Score |
|--------|-------|
| **RMSE** | 2.54 |
| **MAE**  | 1.30 |

The model demonstrates strong performance in estimating basket sizes within a small average margin of error.

---

## ⚙️ How to Run

Make sure you have installed the required dependencies:

<pre> ```bash pip install -r requirements.txt ``` </pre>

ℹ️ Note: You may need to adjust the file paths inside the script of Dataroid__Pipeline.py (main() function) to match your local project structure if the dataset is stored in a different location.

Then run the full pipeline using the command below:

 python Dataroid__Pipeline.py

## This script will:

- Load and preprocess the data using PySpark and Pandas

- Train a baseline CatBoostRegressor model

- Perform hyperparameter optimization using Optuna

- Evaluate the best model on the test set

- Save the trained model as best_model.pkl

- Print the test set RMSE and MAE to the console
