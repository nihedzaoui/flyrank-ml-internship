# Prompt Ladder: Improving an ML Portfolio Case Study Prompt

## Objective

This document shows how a weak AI prompt can be improved step by step by changing one element at a time. Each version is tested, compared, and analyzed to understand which prompt engineering technique improves the output.
## Domain

Machine Learning Engineering Portfolio / Case Study Creation

## Why I chose this task

As an ML Engineering intern, I often need to communicate my projects clearly to technical recruiters and AI engineering managers. This prompt ladder explores how prompt engineering can improve the quality of an AI-generated machine learning case study.

### Prompt Used

Write a case study about my machine learning project.

## Output
Prompt Used

Write a case study about my machine learning project.

AI Output
Machine Learning Project Case Study
Overview

This project focuses on developing a machine learning solution to analyze data and make predictions using advanced algorithms.

The objective was to apply machine learning techniques to solve a real-world problem by using data preprocessing, model training, and evaluation methods.

Methodology

The project followed a typical machine learning workflow:

Data collection and preparation
Data cleaning and preprocessing
Training different machine learning models
Evaluating model performance
Selecting the best-performing approach

Several machine learning algorithms were explored to identify the model that provides the most accurate predictions.

Results

The developed model was able to learn patterns from the dataset and generate predictions. The project demonstrates the ability of machine learning techniques to transform raw data into useful insights.

Conclusion

This project highlights the importance of machine learning in solving real-world problems. It provided experience in data analysis, model development, and performance evaluation.

Analysis of Version 1

Strengths:

Provides a basic structure for a case study.
Mentions common ML workflow steps.

Weaknesses:

Too generic and could apply to any ML project.
Does not mention the actual project objective (bankruptcy prediction).
Does not describe the dataset, models, or technical decisions.
Does not show ML engineering skills.
Not suitable for a professional portfolio aimed at recruiters.

Main lesson:
A vague prompt produces a generic response. The AI needs more context about the project and the intended audience to create a valuable portfolio case study.

### Analysis

The first prompt produced a generic case study. Although it describes a typical machine learning workflow, it does not include important details about my actual project.

Problems identified:
- No project context
- No dataset information
- No ML algorithms mentioned
- No explanation of technical decisions
- No target audience definition

This version is useful as a baseline to compare improvements in later prompt versions.

##Version 2 — Adding Context
Goal of this step

Improve the prompt by adding only one new element: project context.

The first version was too generic because the AI did not know what your ML project was about.

Prompt Used

Write a case study about my machine learning project. The project predicts company bankruptcy using financial data.

AI Output
Case Study: Company Bankruptcy Prediction Using Machine Learning
Overview

This project focuses on developing a machine learning model to predict whether a company is likely to experience bankruptcy based on financial data.

The objective is to use historical financial information to identify patterns that can indicate financial difficulties and help support early risk detection.

Methodology

The project follows a machine learning workflow:

Data preprocessing and cleaning
Exploratory data analysis
Training classification models
Evaluating model performance
Selecting the best-performing model

Different machine learning algorithms were tested to determine which approach provides the most accurate bankruptcy predictions.

Results

The developed model was able to analyze financial indicators and classify companies according to their bankruptcy risk.

The project demonstrates how machine learning can be applied in the financial domain to support decision-making and risk analysis.

Conclusion

This project shows the potential of machine learning for predicting financial problems before they occur. It provides experience in applying classification techniques to real-world financial data.

Analysis of Version 2

Improvements compared to Version 1:

The AI understands the project domain (finance).
The output is more specific to bankruptcy prediction.
The problem becomes clearer.

Remaining limitations:

The technical details are still missing.
No information about:
Dataset size and features
Class imbalance problem
Feature engineering
Models tested (Random Forest, XGBoost, etc.)
Evaluation metrics
The output is still too general for an ML engineering portfolio.

Main lesson:
Adding project context improves relevance, but the AI still needs more instructions about the technical depth and target audience.


##Version 3 — Adding Audience
Goal of this step

Improve the prompt by adding only one new element: the target audience.

Version 2 gave the AI information about the project, but it did not explain who will read the case study. Adding the audience helps the AI choose the right level of detail and writing style.

Prompt Used

Write a machine learning portfolio case study about my company bankruptcy prediction project. Write it for technical recruiters and AI engineering managers evaluating an ML engineering intern.

AI Output
Case Study: Predicting Company Bankruptcy Using Machine Learning
Project Overview

The objective of this project was to build a machine learning classification system capable of predicting whether a company is at risk of bankruptcy using financial indicators.

This project demonstrates an end-to-end machine learning workflow, including data analysis, preprocessing, model development, and evaluation.

Problem Statement

Financial instability can negatively impact investors, companies, and decision-makers. Traditional financial analysis can be time-consuming when analyzing large amounts of financial data.

The goal of this project was to develop a predictive model that can identify potential bankruptcy risks based on historical financial information.

Technical Approach

The project followed several ML engineering steps:

Exploratory Data Analysis (EDA) to understand financial patterns
Data preprocessing to prepare the dataset
Training multiple classification algorithms
Comparing model performance
Selecting the most suitable model based on evaluation metrics

Models explored included:

Random Forest
XGBoost
Gradient Boosting
Support Vector Machine
Evaluation

The models were evaluated using classification metrics:

Accuracy
Precision
Recall
F1-score
ROC-AUC

Because bankruptcy cases were rare compared to healthy companies, evaluation focused on detecting the minority class effectively.

Skills Demonstrated

This project demonstrates experience in:

Building machine learning pipelines
Handling classification problems
Selecting appropriate evaluation metrics
Comparing ML algorithms
Applying machine learning to real-world business problems
Conclusion

This project shows how machine learning can support financial risk analysis by transforming company data into predictive insights. It highlights the ability to design and implement an ML solution from data preparation to model evaluation.

Analysis of Version 3
Improvements compared to Version 2:

✅ The output is now written for a professional audience.
✅ It highlights ML engineering skills instead of only describing the project.
✅ Technical concepts and tools are introduced.
✅ The structure becomes closer to a portfolio case study.

Remaining limitations:
The case study still lacks detailed storytelling.
The ML decisions are not deeply explained.
Missing important project details:
Dataset information (6,819 records, 96 features)
Class imbalance ratio
SMOTE technique
Feature engineering steps
Hyperparameter tuning
Business impact
Main lesson:

Defining the audience changes the output focus. The AI now writes for recruiters instead of producing a generic project description.


##Version 4 — Adding Structure Requirements
Goal of this step

Improve the prompt by adding only one new element: a clear structure.

Version 3 improved the audience and tone, but the output still lacked a complete case study format. Adding sections forces the AI to cover important elements required in a professional ML portfolio.

Prompt Used

Write a professional ML engineering case study about my company bankruptcy prediction project for technical recruiters. Structure it with: problem statement, dataset, methodology, feature engineering, model selection, evaluation, challenges, business impact, and future improvements.

AI Output
Case Study: Predicting Company Bankruptcy Using Machine Learning
Project Overview

This project focuses on developing a machine learning classification system to predict company bankruptcy using financial indicators.

The objective was to transform financial data into a predictive model capable of identifying companies at risk and supporting early financial risk assessment.

Problem Statement

Companies and investors need reliable methods to detect financial difficulties before bankruptcy occurs.

Traditional financial analysis requires manual examination of multiple financial indicators, making it difficult to process large-scale data efficiently.

The goal of this project was to develop an automated machine learning solution that predicts bankruptcy risk using historical financial data.

Dataset

The project used the Company Bankruptcy Prediction dataset containing:

6,819 company records
96 financial features
Binary classification target:
0 → Healthy company
1 → Bankrupt company

A major challenge was the strong class imbalance:

Healthy companies: approximately 96.77%
Bankrupt companies: approximately 3.23%
Methodology

The machine learning pipeline included:

Exploratory Data Analysis (EDA)
Data preprocessing
Feature engineering
Handling class imbalance
Model training
Model evaluation
Hyperparameter optimization
Feature Engineering

Additional financial indicators were created to improve model understanding:

Leverage Ratio to measure debt dependency
Return on Assets (ROA) to evaluate profitability efficiency

Feature engineering helped extract meaningful financial patterns related to bankruptcy risk.

Handling Class Imbalance

Since bankrupt companies represented a small percentage of the dataset, the model could become biased toward predicting healthy companies.

To address this challenge:

SMOTE (Synthetic Minority Oversampling Technique) was applied.
Synthetic samples were generated to improve minority-class recognition.
Model Selection

Several classification algorithms were tested:

Random Forest
XGBoost
Gradient Boosting
AdaBoost
Support Vector Machine (SVC)
K-Nearest Neighbors (KNN)
Gaussian Naive Bayes

Models were compared to identify the best approach for bankruptcy prediction.

Evaluation

The models were evaluated using:

Accuracy
Precision
Recall
F1-score
ROC-AUC
Confusion Matrix

Since detecting bankrupt companies was the main objective, recall and F1-score were considered important evaluation criteria.

Challenges
Challenge	Solution
Highly imbalanced dataset	Applied SMOTE
Many financial variables	Used feature importance analysis
Model selection	Compared multiple algorithms
Avoiding overfitting	Applied validation and hyperparameter tuning
Business Impact

The project demonstrates how machine learning can support financial decision-making by:

Detecting companies at risk earlier
Supporting investment analysis
Reducing manual financial evaluation effort
Providing data-driven risk assessment
Future Improvements

Future extensions could include:

Developing an interactive Power BI dashboard
Deploying the model using an API
Adding Explainable AI techniques such as SHAP
Integrating real-time financial data
Creating a decision-support application
Analysis of Version 4
Improvements compared to Version 3:

✅ The output now follows a professional case study structure.
✅ Important ML engineering steps are clearly presented.
✅ Challenges and solutions are included.
✅ The project is easier for recruiters to evaluate.

Remaining limitations:
The writing is still generated from instructions rather than a strong expert perspective.
The AI does not yet emphasize:
My personal contribution
Engineering decision-making
Lessons learned
Portfolio storytelling
Some sections could be more concise and impactful.
Main lesson:

Adding structure improves completeness and organization. However, to create a strong portfolio case study, the prompt must also define the AI’s role, writing constraints, and expected quality level.


##Version 5 — Final Optimized Output
AI Output
Case Study: Predicting Company Bankruptcy Using Machine Learning
Project Overview

Financial risk assessment is a critical challenge for companies, investors, and financial institutions. This project focuses on developing a machine learning classification system capable of predicting company bankruptcy using financial indicators.

The objective was to design an end-to-end ML pipeline that analyzes historical financial data, identifies risk patterns, and predicts whether a company is likely to experience financial distress.

This project demonstrates my ability to apply machine learning techniques to a real-world financial problem, from data exploration and preprocessing to model optimization and evaluation.

Problem Statement

Traditional bankruptcy analysis relies heavily on manual financial statement analysis, which can be time-consuming and difficult to scale.

The challenge was to answer:

Can machine learning models identify companies at risk of bankruptcy based on their financial characteristics?

The goal was to create a predictive model that could support early risk detection and assist financial decision-making.

Dataset Description

The project used the Company Bankruptcy Prediction dataset.

Dataset characteristics:

6,819 company records
96 financial features
Binary classification target:
0: Healthy company
1: Bankrupt company

The dataset presented a significant challenge due to class imbalance:

Healthy companies: 96.77%
Bankrupt companies: 3.23%

This imbalance required specific techniques to ensure the model could correctly identify bankruptcy cases.

Exploratory Data Analysis (EDA)

The first step was understanding the structure and behavior of financial variables.

EDA focused on:

Feature distributions
Missing value analysis
Correlation analysis
Identification of important financial indicators
Understanding relationships between financial ratios and bankruptcy risk

The analysis revealed that profitability, liquidity, and leverage-related indicators were important factors influencing bankruptcy prediction.

Data Preprocessing

Before training the models, several preprocessing steps were applied:

Data cleaning
Feature analysis
Dataset preparation
Train-test splitting
Transformation of financial indicators into meaningful variables

The goal was to create a reliable dataset suitable for machine learning algorithms.

Feature Engineering

To improve model performance, additional financial indicators were created:

Leverage Ratio

Used to measure the company's dependence on debt and evaluate financial risk.

Return on Assets (ROA)

Used to measure profitability efficiency by analyzing how effectively companies generate profit from their assets.

These engineered features helped models better capture relationships between financial health and bankruptcy risk.

Handling Class Imbalance

A major challenge was the low number of bankruptcy cases compared to healthy companies.

Without correction, models could achieve high accuracy while failing to detect bankrupt companies.

To solve this issue:

SMOTE (Synthetic Minority Oversampling Technique) was applied.

This method generated synthetic examples of minority-class observations, improving the model's ability to recognize bankruptcy cases.

Machine Learning Models Tested

Several classification algorithms were implemented and compared:

Random Forest
XGBoost
Gradient Boosting
AdaBoost
Support Vector Machine (SVC)
K-Nearest Neighbors (KNN)
Gaussian Naive Bayes

Different models were evaluated to determine the best approach for financial risk prediction.

Model Optimization

Hyperparameter optimization was performed using:

GridSearchCV

This process allowed the identification of better model configurations by testing different parameter combinations.

The final pipeline included:

Data preprocessing
Feature engineering
SMOTE balancing
Model training
Hyperparameter tuning
Performance evaluation
Evaluation Metrics

Because bankruptcy detection is a high-risk classification problem, accuracy alone was not sufficient.

The models were evaluated using:

Accuracy
Precision
Recall
F1-score
ROC-AUC
Confusion Matrix

Special attention was given to recall and F1-score because correctly identifying financially distressed companies was the main objective.

Challenges and Solutions
Challenge	Solution
Severe class imbalance	Applied SMOTE
Large number of financial variables	Used feature importance analysis
Selecting the best algorithm	Compared multiple ML models
Preventing overfitting	Used validation and hyperparameter tuning
Business Impact

This project demonstrates how machine learning can support financial decision-making by:

Detecting early warning signals of bankruptcy
Helping analysts evaluate financial risk
Reducing manual analysis effort
Supporting data-driven investment decisions

A deployed version could help financial analysts assess company risk automatically through an interactive dashboard or prediction API.

Technical Skills Demonstrated

Through this project, I developed experience in:

Machine Learning
Classification algorithms
Ensemble learning
Model evaluation
Hyperparameter optimization
Data Science
Exploratory Data Analysis
Feature engineering
Data preprocessing
Handling imbalanced datasets
Tools & Technologies
Python
Pandas
NumPy
Scikit-learn
XGBoost
Matplotlib
Seaborn
Future Improvements

Possible future developments include:

Building a Power BI financial risk dashboard
Deploying the model using FastAPI
Adding Explainable AI techniques (SHAP/LIME)
Integrating real-time financial data
Developing a complete financial risk assessment platform
