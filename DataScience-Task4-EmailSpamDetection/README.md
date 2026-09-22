# Email Spam Detection using Machine Learning

## Oasis Infobyte Data Science Internship

**Track:** Data Science  
**Task:** Task 4 — Email Spam Detection  
**Author:** Mohamed Zufar

## Project Overview

This project develops a machine learning-based SMS spam detection system that classifies messages into HAM (legitimate) and SPAM (unwanted/promotional) categories.

The project includes data cleaning, exploratory data analysis, text preprocessing, TF-IDF feature extraction, model training, evaluation, threshold optimization, error analysis, and deployment preparation.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- TF-IDF
- Multinomial Naive Bayes
- Logistic Regression
- Joblib
- Google Colab

## Dataset

**SMS Spam Collection Dataset**

After cleaning:

- Total messages: 5,169
- HAM: 4,516
- SPAM: 653

## Machine Learning Workflow

Dataset  
↓  
Data Cleaning  
↓  
Exploratory Data Analysis  
↓  
Text Preprocessing  
↓  
Train / Test Split  
↓  
TF-IDF Feature Extraction  
↓  
Model Training  
↓  
Model Evaluation  
↓  
Threshold Optimization  
↓  
Error Analysis  
↓  
Final Evaluation  
↓  
Deployment Model  
↓  
Model Saving & Loading  
↓  
New Message Prediction

## Models

### Multinomial Naive Bayes

Used as the primary text classification model.

### Logistic Regression

Used as an alternative model for comparison.

## TF-IDF Configuration

- Maximum features: 5,000
- N-gram range: 1–2
- Unigrams and bigrams

## Model Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Multinomial Naive Bayes | 96.52% | 100.00% | 72.52% | 84.07% |
| Logistic Regression | 96.42% | 98.96% | 72.52% | 83.70% |

## Threshold Optimization

The default classification threshold of 0.50 was evaluated using a separate validation set.

The final threshold selected was **0.20**.

| Metric | Threshold 0.50 | Threshold 0.20 |
|---|---:|---:|
| Accuracy | 96.52% | 97.39% |
| SPAM Precision | 100.00% | 96.43% |
| SPAM Recall | 72.52% | 82.44% |
| SPAM F1-Score | 84.07% | 88.89% |

## Final Test Results

| Metric | Result |
|---|---:|
| Accuracy | 97.39% |
| Precision | 96.43% |
| Recall | 82.44% |
| F1-Score | 88.89% |

### Confusion Matrix

| | Predicted HAM | Predicted SPAM |
|---|---:|---:|
| Actual HAM | 899 | 4 |
| Actual SPAM | 23 | 108 |

## Error Analysis

The remaining errors were analysed using false-positive and false-negative predictions.

The model had difficulty with short messages, conversational-looking spam, promotional messages with unusual wording, and service-related messages.

Some legitimate messages were incorrectly classified as spam because they contained product, promotional, or call-related vocabulary.

## Deployment

The deployment model was retrained using all 4,135 non-test training messages.

The classification threshold was fixed at **0.20**.

The following components were saved together:

- Multinomial Naive Bayes model
- TF-IDF vectorizer
- Classification threshold

Deployment artifact:

`model/spam_classifier_deployment.joblib`

## New Message Prediction

Example:

**Message:**

`Congratulations! You won a $1000 prize. Click here to claim now!`

**Prediction:** SPAM

**Spam Probability:** 97.49%

## Project Structure

```text

DataScience-Task4-EmailSpamDetection/
│
├── Email_Spam_Detection.ipynb
├── README.md
│
├── model/
│   └── spam_classifier_deployment.joblib
│
└── screenshots/

