# Mobile Plan Recommendation System

## Introduction

Mobile carrier Megaline has identified that many of their subscribers are still using legacy plans. To encourage the adoption of their newer plans, Megaline wants to develop a machine learning model that can analyze subscribers' behavior and recommend one of the new plans: Smart or Ultra.

The primary objective is to create a classification model that can accurately recommend the appropriate plan based on user behavior data. This project utilizes behavioral data from subscribers who have already switched to the new plans. The model should achieve the highest possible accuracy, with a minimum threshold of 75%. The final model's performance will be evaluated using a test dataset.

This notebook will explore and test three different machine learning models (DecisionTreeClassifier, RandomForestClassifier, and LogisticRegression) with varying hyperparameters to determine the best model that meets Megaline's requirements.  

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