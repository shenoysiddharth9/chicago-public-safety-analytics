Data-Driven Public Safety: Predicting Arrest Outcomes in Chicago

Project Overview

This project uses large-scale crime data and machine learning to study a practical public-safety question:

Can we predict whether a reported Chicago crime incident will result in an arrest using information such as crime type, location, time, district, and domestic status?

The project was designed as an end-to-end big-data workflow using Apache Spark and Databricks.

Business / Policy Problem

Public-safety agencies work with large volumes of incident data, but raw records alone do not directly support resource-allocation decisions.

The project focused on:

identifying patterns associated with arrest outcomes;

understanding temporal and geographic differences in crime;

building a scalable predictive model;

translating results into resource-allocation recommendations;

identifying modeling risks such as class imbalance and data leakage.

Data

The project used the Chicago Crime Dataset (2001–2026).

Features included:

crime classification;

location;

district and community area;

incident timestamp;

arrest status;

domestic incident status;

latitude and longitude.

The project presentation reports analysis at multi-million-record scale.

Data Engineering

The data pipeline included:

schema cleaning and column standardization;

null handling;

geographic filtering;

timestamp parsing;

feature engineering;

Spark SQL analysis;

Parquet / Delta Lake storage;

reusable Spark transformations.

Derived features included:

hour of day;

day of week;

year;

time period;

violent-crime indicator;

arrest target variable.

Exploratory Analysis

The project examined:

crime type distributions;

arrest rates by crime type;

district-level patterns;

temporal trends;

late-night and weekend concentration;

geographic differences in arrest outcomes.

An important finding was that high-volume crimes such as theft have low arrest rates, creating substantial class imbalance.

The analysis also identified a potential leakage issue: narcotics incidents had an unusually high arrest rate and therefore required careful treatment in model interpretation.

Machine Learning

Two Spark MLlib classifiers were compared:

Logistic Regression

Random Forest

The workflow used:

an 80/20 train-test split;

StringIndexer;

OneHotEncoder;

VectorAssembler;

cross-validation;

AUC-ROC and additional classification metrics.

Logistic Regression achieved an AUC of approximately 0.867, slightly above the reported Random Forest result.

Business Insights

The model was treated as a decision-support tool, not a deterministic prediction system.

The analysis suggested that public-safety resources could be adapted based on:

crime type;

district-level arrest gaps;

time of day;

weekend / late-night patterns;

violent-crime concentration.

The project also emphasized the importance of reviewing false negatives, class imbalance, leakage, and fairness before any operational deployment.

Tools & Technologies

Python

PySpark

Apache Spark

Spark SQL

Spark MLlib

Databricks

Delta Lake

Parquet

Matplotlib

Machine Learning Pipelines

Repository Structure

├── notebooks/  
│   └── chicago_crime_pipeline.ipynb  
├── report/  
│   └── public_safety_analysis_report.pdf  
├── presentation/  
│   └── final_presentation.pdf  
└── README.md

Team Project

Completed as part of MGMT 59000 – Big Data and MLOps at Purdue University.

Team members listed in the project report:

Siddharth Shenoy

Yash Naidu Avula

Prabhu Ramana Sana

Fabian Macias Peñalosa
