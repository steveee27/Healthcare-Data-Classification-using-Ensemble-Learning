# Healthcare Data Classification Using Ensemble Learning

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Data Preprocessing](#data-preprocessing)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [License](#license)

## Introduction

This project involves applying ensemble learning techniques to predict medical test results, categorized as **Normal**, **Abnormal**, and **Inconclusive**. The dataset, which simulates healthcare records, is used to predict the outcomes of medical tests based on patient information, such as age, gender, medical conditions, and billing amounts.

The machine learning models used for classification include **Bagging Classifier**, **Random Forest**, **AdaBoost**, and **Stacking Classifier**. The goal is to understand which machine learning technique provides the best predictive accuracy for classifying test results.

## Dataset Overview

The dataset consists of 10,000 observations with 15 features, including patient demographics, medical conditions, healthcare billing information, and the target variable (test results). The key features are:

1. **Name**: Name of the patient
2. **Age**: Age of the patient
3. **Gender**: Gender of the patient
4. **Medical Condition**: Diagnosis (e.g., Diabetes, Asthma)
5. **Billing Amount**: Total healthcare bill for the patient
6. **Medication**: Medication prescribed
7. **Test Results**: Outcome of the medical tests (Normal, Abnormal, Inconclusive)

The dataset is structured to simulate patient records, providing insight into various aspects of healthcare diagnostics.

## Data Preprocessing

Data preprocessing is crucial to prepare the dataset for modeling:
- **Handling Missing Values**: Any missing or anomalous values were removed or imputed, particularly in critical columns like `Billing Amount` and `Test Results`.
- **Feature Encoding**: Non-numeric columns like `Gender`, `Medical Condition`, and `Medication` were encoded using One-Hot Encoding and Label Encoding, making the data usable for machine learning algorithms.
- **Scaling**: Numerical features like `Age` and `Billing Amount` were normalized using Min-Max scaling, ensuring that all features are on the same scale and contributing equally to model performance.

## Feature Engineering

Feature engineering was performed to derive meaningful information from the dataset:
- **Duration of Stay**: Calculated from the *Admission Date* and *Discharge Date*, indicating the duration of hospital stay.
- **Categorical Features**: Features such as `Gender`, `Medical Condition`, and `Medication` were converted into binary or one-hot encoded format for compatibility with machine learning models.

The features were then organized and split into training and test datasets, which were used for model training and evaluation.

## Modeling

For this project, several ensemble learning models were trained and compared:
- **Bagging Classifier**: Base estimators include Decision Trees, SVC, and KNN. It helps in reducing variance and improving stability by training multiple models.
- **Random Forest**: An ensemble of decision trees, trained using bootstrapping and random feature selection.
- **AdaBoost**: A boosting algorithm that combines weak learners to create a strong classifier.
- **Stacking Classifier**: A model that combines different classifiers (like Random Forest and SVC) in a way that each classifier’s strengths complement one another.

The models are trained using the training dataset and evaluated on the test dataset.

## Model Evaluation

Each model's performance was evaluated using key metrics:
- **Confusion Matrix**: To visualize how well the model performs across the different categories of test results.
- **F1-Score**: To measure the model’s ability to correctly classify instances across the classes.
- **Precision and Recall**: To assess the trade-off between false positives and false negatives.


### Model Performance Summary:
Here is a table summarizing the performance of each model and the parameters used:

![image](https://github.com/user-attachments/assets/9006701c-c628-4beb-b492-41df9af573f2)

- **Bagging Classifier**: The best performance was achieved with **Decision Tree** as the base estimator, with an F1-Score of **0.35**.
- **Random Forest**: Max depth set to **10** with **Gini** criterion, achieving an F1-Score of **0.34**.
- **AdaBoost**: Performed reasonably well with an F1-Score of **0.33**, but lagged behind the other models.
- **Stacking Classifier**: Combining **Random Forest** and **SVC**, this model achieved the best F1-Score of **0.35**.

## Results

The ensemble learning models demonstrated decent performance in classifying medical test results:
- **Bagging Classifier** and **Stacking Classifier** performed the best with an F1-Score of **0.35**.
- **Random Forest** and **AdaBoost** performed slightly worse, though still providing valuable insights into the classification task.

### Final Model Selection
Based on the results, **Stacking Classifier** and **Bagging Classifier** are the top-performing models, yielding the highest F1-Score of **0.35**. These models were able to effectively classify the medical test results into *Normal*, *Abnormal*, and *Inconclusive* categories.

## Conclusion

This project demonstrates the use of ensemble learning methods to classify healthcare data. While the models performed well, further improvements can be made by tuning hyperparameters, adding more relevant features, or exploring other advanced techniques like deep learning.

- **Bagging** and **Stacking** classifiers provide the best predictive performance for medical test classification.
- **AdaBoost** and **Random Forest** performed moderately well but can benefit from further tuning.

Future work will focus on improving the model’s accuracy by incorporating more features, fine-tuning model parameters, and exploring alternative classification techniques.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
