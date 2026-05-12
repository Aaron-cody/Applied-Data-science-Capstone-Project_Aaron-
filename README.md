# Applied Data Science Capstone: SpaceX Falcon 9 Launch Success Prediction

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