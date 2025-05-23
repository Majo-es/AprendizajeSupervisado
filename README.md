# Medical Cost Analysis: Prediction & Classification
This project leverages supervised learning techniques to analyze a medical cost dataset. It aims to both predict continuous medical charges and classify costs into distinct categories.

## Project Overview
The core of this project involves:

- **Data Loading and Exploration**: Initial steps include loading the dataset and performing exploratory data analysis (EDA) with various visualizations to understand the data's characteristics.
- **Model Building**: Developing and evaluating machine learning models for two distinct tasks: regression and classification.
  
## Models Used
1. **Linear Regression** (for predicting 'charges')

**Purpose**: To predict continuous medical charges based on patient attributes like age, BMI, smoker status, and more.

**Implementation Details**:
A `sklearn.pipeline.Pipeline` is constructed to streamline the data processing and model training. This pipeline includes:

- **Preprocessing**:
  - `sklearn.preprocessing.OneHotEncoder` for nominal categorical features (sex, smoker, region).
  - `sklearn.preprocessing.StandardScaler` for numerical features (age, BMI, children) to standardize their scale.
  - `sklearn.impute.SimpleImputer` to handle any missing values in the dataset.
- **Model**: A `sklearn.linear_model.LinearRegression` model trained on the preprocessed data.
  
**Evaluation**:
The model's performance is assessed using `Mean Squared Error (MSE)` and `R-squared (R²)` on both the training and test datasets.

2. **Classification Models** (for predicting 'charges_group')
   
**Purpose**: To categorize medical costs into three distinct groups (low, medium, and high) based on the same patient features.

**Implementation Details**:
- A new categorical feature, `charges_group`, is created by binning the continuous 'charges' into three defined cost categories.
- Similar preprocessing steps to the **Linear Regression** pipeline are applied to the data.
- The following classification algorithms are trained and evaluated:
  - `sklearn.tree.DecisionTreeClassifier`
  - `sklearn.ensemble.RandomForestClassifier`
  - `sklearn.linear_model.LogisticRegression`

**Evaluation**:
Model performance is evaluated using standard classification metrics, including:
- `Accuracy`
- `Precision`
- `Recall`
- `F1-score`
- `Confusion matrices` are also used to visualize the models' predictive performance for each category.

Sequence diagram illustrating the data flow and model training process:
<img width="1153" alt="Medical Cost Analysis" src="https://github.com/user-attachments/assets/3389411a-4837-47cb-9767-18ad2eeb61c8" />
