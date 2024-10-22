# Binary Prediction of Poisonous Mushrooms

Welcome to the **2024 Kaggle Playground Series**! This project is focused on predicting whether a mushroom is edible or poisonous based on its physical characteristics. The competition is hosted on Kaggle, and the objective is to build a machine learning model that can make accurate predictions using the provided dataset.

## Project Overview

- **Competition Name**: Binary Prediction of Poisonous Mushrooms
- **Goal**: Predict whether a mushroom is edible (`e`) or poisonous (`p`) based on physical characteristics.
- **Evaluation Metric**: Submissions are evaluated using the **Matthews correlation coefficient (MCC)**.
- **Dataset**: The dataset is synthetically generated from real-world data, ensuring test labels are not publicly available.

## Timeline

- **Start Date**: August 1, 2024
- **Final Submission Deadline**: August 31, 2024

## Project Structure

- **Input Data**
  - `Input Data.rar`: Compressed archive containing all the necessary datasets (`train.csv`, `test.csv`, `sample_submission.csv`, and `original_data.csv`).
  
- **Notebooks**
  - `EDA.ipynb`: Exploratory Data Analysis to understand the dataset, including data cleaning and visualization.
  - `Model Training.ipynb`: Training the machine learning model using XGBoost and CatBoost, performing cross-validation, and generating predictions.

- **Outputs**
  - `submission.csv`: The final submission file in the required format.
  
- **Configuration**
  - `.gitignore`: Ensures that unnecessary files such as `catboost-info` and large data files are not tracked by Git.
  - `requirements.txt`: Lists all the dependencies required to run the project.

## Handling Input Data

### Step 1: Extract the Compressed Data

The input data is provided as a compressed `.rar` file. Before running any of the notebooks, you'll need to extract the data:

1. Use a file extraction tool such as WinRAR, 7-Zip, or any other compatible software.
2. Extract the contents of `Input Data.rar` into the `Input Data` directory.

### Step 2: Verify the Files

After extraction, ensure that the following files are present inside the `Input Data` directory:

- `original_data.csv`
- `sample_submission.csv`
- `test.csv`
- `train.csv`

These files are required for data exploration, model training, and submission generation.

## Requirements

Install the necessary dependencies using the following command:

```bash
pip install -r requirements.txt
```

## Model Training

This project leverages two powerful gradient boosting algorithms to predict mushroom edibility:

- **XGBoost**: Implemented with GPU acceleration for faster training.
- **CatBoost**: Known for its excellent handling of categorical features.

### Preprocessing

- **Numerical Features**: Standardized using `StandardScaler` to ensure that all features contribute equally to the model.
- **Categorical Features**: One-hot encoded using `OneHotEncoder` to convert categorical variables into a format suitable for machine learning algorithms.

### Cross-Validation

- **Stratified K-Fold**: 5-fold cross-validation is employed to ensure robust model performance across different data splits, preserving the proportion of classes in each fold.

### Evaluation

The model's performance is evaluated using the **Matthews correlation coefficient (MCC)**, a metric particularly useful for imbalanced datasets. The MCC provides a balanced measure that takes into account true and false positives and negatives, making it ideal for evaluating binary classification tasks.

### Submission

The predictions are formatted as follows:

```csv
id,class
3116945,e
3116946,p
3116947,e
...

