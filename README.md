# Capstone-Luxury-Handbag-Pricing
Hedonic regression and ML models for luxury handbag resale price (Hermès, Chanel, LV, Dior)


## Overview

This repository contains the full analytical code supporting a thesis on price formation in the secondary luxury handbag market. The study combines hedonic OLS regression, Random Forest, and XGBoost with SHAP interpretability to identify the attributes that drive resale prices across four major luxury brands.

## Data

- **Sources:** Farfetch and The RealReal (resale listings); brand websites, Wayback Machine and Sotheby's editorial (retail benchmarks)
- **Brands:** Hermès, Chanel, Louis Vuitton, Dior
- **Sample:** n = 296 listings after cleaning
- **Target variable:** log(resale price) in EUR

## Repository Contents

`Capstone_Code.ipynb` contains the full analytical pipeline, organised in five parts. Part 1 covers data cleaning and exploratory data analysis, including normalisation of color, material, condition, and accessory variables, as well as visualisations of price distributions by brand, model, material, and platform. Part 2 implements feature engineering and the OLS hedonic baseline model with HC3 robust standard errors, including coefficient interpretation, residual diagnostics, and model evaluation. Part 3 trains and tunes Random Forest and XGBoost models via GridSearchCV. Part 4 applies SHAP to the final XGBoost model to interpret global feature importance and non-linear effects. Part 5 benchmarks resale prices against retail prices using resale-to-retail ratios and CAGR analysis.

`resale_listings.csv` contains the raw resale listing data collected manually from Farfetch and The RealReal. `Retail_dataset.xlsx` contains retail price benchmarks collected manually from brand websites, Wayback Machine and Sotheby's.

## Key Findings

- Brand is the primary structural driver of resale price: Hermès secondary market prices systematically exceed retail
- Exotic materials (crocodile, alligator) command the highest price premiums (+150%), followed by condition score and original packaging (includes box: +21%)
- Smaller sizes show higher resale-to-retail ratios due to strong demand dynamics; neutral colors, especially black, mitigate depreciation risk
- XGBoost outperforms OLS, confirming non-linear price dynamics and a three-stage bag lifecycle captured by SHAP
- Platform selection matters: The RealReal listings are priced significantly lower than Farfetch equivalents

## Requirements

All code runs in Google Colab. Main libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`, `shap`, `statsmodels`, `scipy`, `math`, `pickle`
