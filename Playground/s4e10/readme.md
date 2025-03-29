# Playground Series - S4E10: Kaggle Competition

![image](https://github.com/user-attachments/assets/578e29ab-083c-418b-a280-13f7590b2fa0)

This repository contains my work on the [Playground Series - S4E10](https://www.kaggle.com/competitions/playground-series-s4e10) Kaggle competition. In this project, I performed exploratory data analysis (EDA) and built a Random Forest model that achieved a ROC AUC score of **0.8657**. There are other models trained as well such as Neural network and Logistic Regression, but not as accurate.                                             

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [🏦 Loan Prediction Dataset Column Description](#-loan-prediction-dataset-column-description)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Modeling](#modeling)
  - [Random Forest](#random-forest)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

The goal of this competition is to build a predictive model based on a provided dataset. The challenge involves exploring the data, handling missing values, feature engineering, and ultimately training a model to maximize the ROC AUC score on the validation set.

This project documents the process from initial data exploration to model training and evaluation. I experimented with different approaches, and my best performing model is a Random Forest classifier that reached a ROC AUC of **0.8657**.

## Dataset

The dataset for this competition can be downloaded from the [Kaggle competition page](https://www.kaggle.com/competitions/playground-series-s4e10). It includes:

- **Training Data:** Labeled examples for building the model.
- **Test Data:** Unlabeled examples for generating predictions.
- **Supplementary Files:** Additional documentation and data dictionaries.

> **Note:** Make sure to abide by the competition rules and data usage policies when using the dataset.

## 🏦 Loan Prediction Dataset Column Description

| Column Name                        | Description 🌟 | Effect on Loan Decision 📊 |
|------------------------------------|---------------------------------------------|--------------------------------------------------|
| **person_age** 🧑‍🦳🧑‍🦰 | Age of the loan applicant. | Younger applicants may have shorter credit histories, while older applicants may have more financial stability. |
| **person_income** 💰 | Applicant’s annual income. | Higher income increases the likelihood of loan approval, as it suggests better repayment capacity. |
| **person_home_ownership** 🏡 | Whether the applicant owns a home or rents. | Homeowners are often seen as more financially stable, reducing loan risk. |
| **person_emp_length** 🏢⌛ | Number of years the person has been employed. | Longer employment history suggests financial stability and reliability. |
| **loan_intent** 🎯 | Purpose of the loan (education, medical, business, etc.). | Some purposes (e.g., business or medical) might carry higher risk than others (e.g., home improvement). |
| **loan_grade** 🔠 | Creditworthiness rating of the loan (A to F). | A higher grade (A, B) means lower risk and better terms, while lower grades (E, F) indicate higher risk. |
| **loan_amnt** 💸 | Total amount requested for the loan. | Higher amounts increase lender risk, especially if not backed by strong income or credit history. |
| **loan_int_rate** 📉📈 | Interest rate on the loan. | Higher interest rates may indicate higher risk borrowers, affecting affordability. |
| **loan_percent_income** 📊 | Loan amount as a percentage of income. | If the loan is a large portion of the applicant's income, it may signal repayment difficulties. |
| **cb_person_default_on_file** ⚠️📁 | Whether the person has previously defaulted (Yes/No). | A past default history significantly increases loan risk and may lead to rejection. |
| **cb_person_cred_hist_length** ⏳ | Length of the person’s credit history (years). | Longer credit history usually indicates a more reliable borrower. |
| **loan_status** ✅❌ | Whether an applicant is approved for loan (1) or not (0). | Target variable used for predicting loan approval likelihood. |

💡 **Key Insights:**  
- Higher income, homeownership, long employment, and a good credit history **increase** approval chances.  
- High loan amounts, high debt-to-income ratio, or past defaults **increase** the risk of rejection.  
- Loan purpose and grade also play a crucial role in decision-making.  

## Exploratory Data Analysis (EDA)

The EDA phase involved:
- Understanding the distribution of features.
- Visualizing relationships between variables.
- Handling missing values and outliers.
- Identifying potential feature engineering opportunities.

Detailed EDA notebooks are available in the `notebooks/` directory. These notebooks provide insights into the data and justify the subsequent modeling choices.

 used 0.2 of train.csv for validation and the rest fot training the model.

## Modeling

### Random Forest

After trying multiple approaches, I chose a Random Forest classifier due to its robustness and interpretability. Key steps include:

- **Data Preprocessing:** Handling missing values, encoding categorical features, and scaling numerical variables.
- **Feature Engineering:** Creating new features based on domain knowledge.
- **Model Training:** Using scikit-learn’s `RandomForestClassifier`.
- **Evaluation:** The model was evaluated using ROC AUC as the primary metric, achieving a score of **0.8657** on the validation set.

The code for model training and evaluation is documented in the `scripts/` directory.

## Results

- **Best Model:** Random Forest Classifier
- **ROC AUC Score:** 0.8657
- **Feature Importance:** Identified key features impacting loan approval.

## Installation

Clone the repository and install the required dependencies:

```sh
pip install -r requirements.txt
```

## Usage

Run the preprocessing and model training script:

```sh
python train_model.py
```

## Project Structure

```
/
├── notebooks/    # Jupyter Notebooks for EDA and experiments
├── scripts/      # Python scripts for preprocessing and training
├── data/         # Dataset (not included in repo)
├── models/       # Saved trained models
├── results/      # Model evaluation results
└── README.md     # Project documentation
```

## Future Work

- Experiment with boosting techniques (XGBoost, LightGBM).
- Perform hyperparameter tuning for improved performance.
- Implement deep learning approaches for further optimization.

## Contributing

Feel free to fork the repository and submit pull requests with improvements!

## License

This project is open-source under the MIT License.

## Acknowledgements

Thanks to Kaggle for hosting this competition and providing the dataset.

