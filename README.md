# 🏠 Housing Property-Price-Prediction-ML-Project

The Problem statement is to **predict the amount of a housing property** based on a range of features such as **_carpet_area_**, **_property_status_**, **_floor_**, **_transaction type_**, **_furnishing_**, **_facing_**, **_overlooking_**, **_society name_**, **_bathroom count_**, **_balcony count_**, **_car parking_**, **_ownership type_**, **_super_area_**, **_property_title_** and **_amount_** of a housing property.

The dataset 📂 can be downloaded from kaggle using this [Link](https://www.kaggle.com/datasets/juhibhojani/house-price)

---

The dataset 📑 consists of the following columns given in the table along with their description

| Column Name       | Description                                                    |
| ----------------- | -------------------------------------------------------------- |
| Index             | Listing index (row number, numeric ID)                         |
| Title             | Listing title/headline (text summary of property)              |
| Description       | Detailed description of the property (text)                    |
| Amount(in rupees) | Total asking price of the property in Indian rupees (₹)        |
| Price (in rupees) | Unit price per area (₹ per square foot)                        |
| location          | Locality or city of the property                               |
| Carpet Area       | Net usable area of the unit (sqft), excluding walls/common     |
| Status            | Property status (e.g. “Ready to Move”)                         |
| Floor             | Floor number (with total floors, e.g. “3 out of 5”)            |
| Transaction       | Sale type (e.g. Resale vs New Property)                        |
| Furnishing        | Furnishing status (Unfurnished, Semi, Furnished)               |
| facing            | Direction the unit faces (e.g. East, North)                    |
| overlooking       | View from the unit (e.g. Garden/Park, Main road)               |
| Society           | Name of the housing society or complex                         |
| Bathroom          | Number of bathrooms in the unit                                |
| Balcony           | Number of balconies in the unit                                |
| Car Parking       | Parking spaces (count and type, e.g. “1 Open”, “2 Covered”)    |
| Ownership         | Ownership type (Freehold vs Leasehold)                         |
| Super Area        | Super built-up area (sqft): carpet area + shared common spaces |
| Dimensions        | Unit dimensions (likely L×W, unclear or missing data)          |
| Plot Area         | Plot area (sqft) of land (mostly blank)                        |

---

## 🔄 Understanding the Lifecycle

The project lifecycle consisted of these steps

```
                         Data Cleaning
                              |
                        Train Test Split
                              |
                    Exploratory Data Analysis
                              |
                       Feature Engineering
                              |
                        Model Training
                              |
          Model Evaluation and Hyperparameter Tuning
```

---

### 🧹 Data Cleaning

- #### **_Why?_**

  - Presence of irrelevant columns in the dataset.
  - Non-uniform naming of columns which needed to be fixed.
  - Ensusring the validity and reliability of the data points.
  - Extraction new columns out of messy columns. (Eg -> Extracting `num_bhk` information out of `Title`)

- #### **_How?_**
  - Python libraries such as `numpy` and `pandas`.

### ✂️ Train Test Split

- #### **_Why?_**

  - To study the patterns and train the model on training dataset only.
  - To tune and evaluate the model performance later on the validation dataset and the test dataset respectively.
  - To ensure that there is no data leakage between the `train`,`test` and `val` sets.

- #### **_How?_**

  - `train_test_split` function from the `model_selection` module of the python library` scikit-learn`.

### 📊 Exploratory Data Analysis

- #### **_Why?_**

  - To understand the patterns in the training dataset in order to make decisions regarding feature engineering or need of further data cleaning.
  - To understand the relationship between different features and their relationship with the target column.
  - To understand the missing values and outliers in the dataset more deeply.

- #### **_How?_**

  - Python libraries for data visualisation such as `matplotlib`,`seaborn` and `pandas`.
  - For missing values analysis `missingno` was used.

### 🛠️ Feature Engineering

- #### **_Why?_**

  - To impute missing values in different columns according to the need.
  - To make our feature set model-friendly.
  - To make new features out of existing ones for better signaling for the models to capture.
  - To rule out some poor features.

- #### **_How?_**

  - Python libraries for feature engineering such as `scikit-learn`,`feature-engnine`,`pandas` and `numpy`.
  - Feature Engineering mainly consisted of **_Missing Value Imputation_**, **_Feature Transformation_**, **_Feature Construction_** and **_Feature Selection_**.
  - **_Feature Transformation_** involved normalizing transformations such as (log,sqrt) and scaling for numerical columns and encoding for categorical columns.
  - **_Feature Construction_** involved constructing new features out of existing ones for better model performance. (Eg -> extracting `area_per_room` feature from already existing `num_bhk`, `super_area` and `carpet_area`)
  - Binning performed in some numerical columns to convert them to categorical.
  - **_Feature Selection_** involved removing some existing features based on poor impact on the target column.
  - Normalization of target column `amount` was done as the column was skewed.

  ### 🤖 Model Training, Evaluation and Hyperparameter Tuning

  - Different machine learning models and hyperparameter combinations were performed and their performance was tracked and evaluated.
  - For **_Hyperparameter Tuning_** a python framework called `optuna` was used.
  - For **_Experimentation Tracking_** a python framework called `mlflow` was used.
  - For optimization `mean_absolute_error` was taken as the metric.
  - In order to avoid overfitting an overfit penalty (absolute difference between the train result and val result) was added to the `root_mean_squared_error`.

---

### 📈 Results

- The resulting model when evaluated on the test set improves model performance by decreasing `root_mean_squared_error` by `52.19 %` and `mean_absolute_error` by `52.87%` compared to the baseline model.
- Baseline model = mean prediction of target column.
- The resulting model explains `77.14 %` variation of target variable in the test dataset.

---

### 📬 Contact

If you liked my work don't forget to ⭐ my repository.

Feel free to connect by email 📧 : ` rishabhpancholi134@gmail.com`.

🔗 Checkout my [LinkedIn](https://www.linkedin.com/in/rishabh-pancholi-9a31b9191/) profile.

---

# 🙏 **_Thank You_**
