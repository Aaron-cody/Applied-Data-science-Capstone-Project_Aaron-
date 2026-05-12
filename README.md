# Applied Data Science Capstone: SpaceX Falcon 9 Launch Success Prediction

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Classification-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Project Overview

This project demonstrates an end-to-end applied data science workflow using SpaceX Falcon 9 launch data. The goal is to predict whether the first stage of a Falcon 9 rocket will land successfully using data collection, data wrangling, exploratory data analysis, geospatial visualization, and machine learning.

## Project Highlights

- Built an end-to-end data science workflow from data collection to model evaluation
- Collected and prepared SpaceX Falcon 9 launch data using web scraping and structured data sources
- Performed exploratory data analysis to identify patterns in launch success
- Created geospatial analysis of launch sites using interactive map visualizations
- Built classification models to predict first-stage landing success
- Connected the technical workflow to business decision-making and risk analytics

## Executive Summary

This project applies an end-to-end data science workflow to predict whether the first stage of a SpaceX Falcon 9 rocket launch will land successfully. The project combines web scraping, data wrangling, exploratory data analysis, geospatial visualization, and machine learning to support data-driven decision-making.

## Business Problem

Rocket launches are expensive, and the ability to reuse the first stage can significantly reduce launch costs. Predicting whether a Falcon 9 first stage will land successfully helps estimate launch cost, assess operational risk, and understand which factors are associated with successful outcomes.

## Project Objective

The objective of this project is to build a machine learning model that predicts Falcon 9 first-stage landing success using launch-related variables such as payload mass, orbit type, launch site, and flight number.

## Methodology

The project follows a structured applied data science workflow:

1. Data collection through web scraping and API-based sources
2. Data cleaning and feature preparation
3. Exploratory data analysis
4. Geospatial launch site analysis
5. Machine learning model development
6. Model evaluation and interpretation

## Repository Structure

```text
.
├── README.md
├── requirements.txt
├── notebooks/
│   ├── 01_web_scraping_data_collection.ipynb
│   ├── 02_data_wrangling.ipynb
│   ├── 03_launch_site_location_analysis.ipynb
│   └── 04_machine_learning_prediction.ipynb
├── figures/
└── reports/