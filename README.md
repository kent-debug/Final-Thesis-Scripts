# Final-Thesis-Scripts
Data-Driven Precision Public Health: Leveraging Machine Learning to Track and Reduce Zero-Dose and Partially Vaccinated Children in Nakifuma, Uganda
Project Overview
This repository contains the core analytical scripts and machine learning workflows developed for the Master of Data Science and Analytics thesis at Uganda Christian University, Department of Computing and Technology.
Despite global progress, 14.3 million children worldwide remain zero-dose and 5.6 million are partially vaccinated. In Uganda, only 54% of children are fully immunized by their first birthday. This project applies data science and machine learning to address a critical gap: the absence of granular, data-driven approaches to identify and target zero-dose, partially vaccinated, and fully immunized children at the community level in Nakifuma Sub-county, Mukono District, Uganda.

Research Objectives

Factor Identification — Identify the socio-demographic, health system, and behavioral factors that significantly distinguish zero-dose (ZD), partially vaccinated (PV), and fully immunized (FI) children using statistical association tests.
Predictive Modeling — Develop and validate machine learning models that accurately predict a child's vaccination status using the identified factors.
Evidence-Based Recommendations — Propose targeted, data-driven intervention strategies derived from model outputs to systematically increase fully immunized coverage.


What the Code Does
Phase 1 — Factor Identification (factor_analysis/)

Loads community survey data collected from 115 caregiver-child pairs in Nakifuma Sub-county (November–December 2024)
Applies chi-square tests for categorical variables and Mann-Whitney U tests for numerical variables at α = 0.05 to identify significant predictors of vaccination status
Uses Random Forest feature importance to rank predictive power of all 35 variables
Outputs: significant predictors per vaccination status group (Tables 1.2, 1.3, 1.4)

Phase 2 — Predictive Modeling (modeling/)

Implements four supervised machine learning algorithms: Logistic Regression, Support Vector Machine (SVM), Gradient Boosting, and Random Forest
Applies stratified 70:30 train-test split to preserve class distribution
Applies SMOTE (Synthetic Minority Over-sampling Technique) to correct class imbalance in the training set
Evaluates models using Precision, Recall, F1-Score, and AUC-ROC
Outputs: model performance metrics (Table 1.5), combined ROC curves (Figure 2.4)

Phase 3 — Geospatial Analysis (geospatial/)

Maps GPS coordinates of sampled households across Nakifuma Sub-county
Visualizes geographic clustering of zero-dose and partially vaccinated children relative to health facility locations
Outputs: geospatial distribution map (Figure 2.3) informing mobile clinic and GIS-based outreach targeting

Phase 4 — Qualitative Analysis (qualitative/)

Processes open-ended caregiver responses using thematic analysis
Generates word cloud visualizations of caregiver feedback by vaccination status group
Outputs: thematic summaries and word clouds informing community-level intervention design


Key Results
Model ZD F1PV F1FI F1
Logistic Regression1.000.710.89
Support Vector Machine0.940.740.71
Gradient Boosting1.000.710.83
Random Forest (Best)0.970.740.94
Key finding: Health system experiential factors — negative health worker attitudes (p=0.013) and long waiting times (p=0.021) — were stronger predictors of zero-dose status than geographic distance (p=0.3145, not significant).

Technical Stack

Language: Python 3.13
Libraries: pandas 2.3.1, scikit-learn, statsmodels, matplotlib, geopandas
Tools: Jupyter Notebooks, Git
Techniques: Univariate statistical testing, SMOTE oversampling, supervised machine learning, geospatial mapping, thematic analysis, ROC-AUC evaluation


Research Impact
This project provides a reproducible, open-source precision public health framework that enables immunization programs to shift from reactive to proactive, predictive approaches. The Random Forest model enables community health workers to triage zero-dose and partially vaccinated children based on readily available community-level data, supporting Uganda's goal of 90% full immunization coverage by 2030.

Authors
Ogwok Kenneth Michael — kogwok@ucu.ac.ug | ORCID: https://orcid.org/0009-0002-9572-4978
Supervisor: Dr. Daphne Nyachaki Bitalo — Uganda Christian University, Department of Computing and Technology

Ethics
Ethical approval was granted by the Uganda Christian University Research Ethics Committee (Approval No. UCUREC-2024-1021). All data is fully anonymized. No personally identifiable information is stored in this repository.
