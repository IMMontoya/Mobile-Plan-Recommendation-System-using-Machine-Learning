# Mobile Plan Recommendation System

## Introduction

Mobile carrier Megaline has identified that many of their subscribers are still using legacy plans. To encourage the adoption of their newer plans, Megaline wants to develop a machine learning model that can analyze subscribers' behavior and recommend one of the new plans: Smart or Ultra.

The primary objective is to create a classification model that can accurately recommend the appropriate plan based on user behavior data. This project utilizes behavioral data from subscribers who have already switched to the new plans. The model should achieve the highest possible accuracy, with a minimum threshold of 75%. The final model's performance will be evaluated using a test dataset.

This notebook will explore and test three different machine learning models (DecisionTreeClassifier, RandomForestClassifier, and LogisticRegression) with varying hyperparameters to determine the best model that meets Megaline's requirements.  

## Dataset

This project utilizes a dataset containing monthly behavioral information about subscribers of Megaline, a mobile carrier. The dataset includes the following features for each user:

- **calls**: Number of calls made.
- **minutes**: Total duration of calls in minutes.
- **messages**: Number of text messages sent.
- **mb_used**: Internet traffic used in megabytes.
- **is_ultra**: Indicator of the plan for the current month (1 for Ultra, 0 for Smart).

### Data Source

The data file, named `users_behavior.csv`, provides insights into user behavior and their respective mobile plans.

### Data Preparation

- **No missing values**: The dataset is complete with no missing values.
- **Class imbalance**: The dataset exhibits a class imbalance, with approximately 30% of users on the Ultra plan and 70% on the Smart plan. This imbalance is managed during the model training process using class weighting.

### Data Splitting

The dataset is divided into three subsets to facilitate model training and evaluation:

- **Training set**: 60% of the data, used for training the models.
- **Validation set**: 20% of the data, used for tuning model hyperparameters.
- **Test set**: 20% of the data, used for evaluating the final model performance.

This structured approach ensures a comprehensive analysis and accurate model development based on user behavior data.

## Model

The objective of this project is to develop a machine learning model to recommend the appropriate mobile plan (Smart or Ultra) based on user behavior. Multiple models were evaluated to determine the best performing model.

### Model Selection

Three different machine learning models were tested:

### Decision Tree Classifier

- **Description**: A simple and interpretable model that splits the data into branches to make predictions.
- **Tuning**: Further tuning was performed by iterating over a range of hyperparameters to optimize performance.
- **Performance**: Achieved an accuracy of 80.25% on the test dataset.
![Decision Tree Classifier Confusion Matrix](/images/DecisionTreeClassifier_cm.png)

### Random Forest Classifier

- **Description**: An ensemble learning method that combines multiple decision trees to improve accuracy and robustness.
- **Tuning**: Hyperparameters such as the number of trees, max_depth, and feature selection were optimized to enhance model performance.
- **Performance**: Showed high accuracy and robustness against overfitting with an accuracy of 82.58%.  
![Random Forrest Classifier](/images/RandomForrestRegression.png)

### Logistic Regression

- **Description**: A linear model used for binary classification that estimates probabilities using the logistic function.
- **Tuning**: Regularization and other hyperparameters were adjusted to achieve the best results.
- **Performance**: Provided a baseline for comparison, with a simpler and faster training process, accuracy of only 74.81%.
![Logistic Regression](/images/LogisticRegression.png)

## Results

- **Best Model**: The Random Forest Classifier was identified as the best performing model with an accuracy of 82.58%. This model successfully balances accuracy and robustness, making it the most suitable for recommending mobile plans based on user behavior.
- **Sanity Checks**: Baseline accuracy for random predictions was 56%, and for constant predictions (majority class) was 69%. Both were significantly lower than the model accuracies, validating the effectiveness of the machine learning approach.
- **Business Objective**: The project successfully met the business requirement of achieving a minimum accuracy of 75%.

### Model Parameters

The optimized parameters for the Random Forest Classifier are as follows:

- `n_estimators`: 100
- `criterion`: 'gini'
- `max_depth`: 12
- `min_samples_split`: 10
- `min_samples_leaf`: 10
- `max_features`: None
- `class_weight`: None

The [best model](BestModel.joblib) is saved in the directory.

## Installation

To run this project, you will need to have [Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html) installed on your machine. Follow the instructions below to set up the environment:

1. Clone the repository:

    ```bash
    git clone https://github.com/IMMontoya/Mobile-Plan-Recommendation-System-using-Machine-Learning.git
    cd Mobile-Plan-Recommendation-System-using-Machine-Learning
    ```

2. Create the conda environment using the provided environment file:

    ```bash
    conda env create -f environment.yml
    ```

3. Activate the conda environment:

    ```bash
    conda activate .conda
    ```

If you encounter any issues or need additional information, refer to the [Conda documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-file-manually).
