#  Delivery Time Prediction (Food Delivery Case Study)

This project is an end-to-end regression pipeline to predict food delivery time (in minutes) using various delivery, customer, and route features. The model is trained using XGBoost with custom feature engineering.

---

##  Problem Statement

Predict the delivery time of an order based on:
- Delivery person characteristics (age, ratings)
- Delivery vehicle type
- Calculated route distance
- Engineered traffic/load features

---

##  Tech Stack

- Python (pandas, seaborn, scikit-learn, XGBoost)
- Jupyter Notebooks
- Geopy (for calculating distance)
- Joblib (for model saving)
- Matplotlib & Seaborn (for visualization)

---

##  Project Structure

##  Project Structure

```

project/
├── data/                                                 # Raw & processed data
│   ├── Food Delivery Time Prediction Case Study.xlsx    # Raw dataset
│   └── cleaned.csv                                      # Cleaned & preprocessed data
│   └── xg.joblib                                        # Trained XGBoost model
├── notebook/                  # EDA and prototyping
│   └── eda.ipynb
├── src/                       # Core modules
│   ├── preprocessing.ipynb
│   ├── training.ipynb

````

##  Features Used

After preprocessing and engineering:
- `Delivery_person_Age`
- `Delivery_person_Ratings` (clipped to [2.5, 5])
- `distance` (computed using lat/lon with geopy)
- `speed` (mapped from vehicle type)
- `traffic_fact` (custom feature: max speed × rating - actual capability)
- `Type_of_vehicle` (label encoded)

---

##  Model

- **Model:** XGBoost Regressor
- **Tuning:** GridSearchCV over `n_estimators`, `max_depth`, `learning_rate`

---

##  How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/delivery-time-prediction.git
   cd delivery-time-prediction
Install requirements:

pip install -r requirements.txt

Run Jupyter notebooks in order:

notebook/eda.ipynb
src/preprocessing.ipynb
src/training.ipynb

The trained model will be saved as data/xg.joblib.

---
Author
Sarfras-[https://www.linkedin.com/in/muhammedsarfras]
