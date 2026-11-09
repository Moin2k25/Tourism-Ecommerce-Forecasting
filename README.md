# Predictive Analytics and Machine Learning in Tourism and E-Commerce

MSc Business Analytics dissertation, University of Exeter (2025)

## Problem

Tourism and e-commerce both depend on good forecasts for pricing, stock and staffing. But their data looks very different. This project asks: **do the same forecasting models work equally well in both sectors, and if not, why?**

## Data

Two public datasets from Kaggle (copies are included in this repo):

| Sector | Dataset | What it contains |
|---|---|---|
| Tourism | [Tourism and Economic Impact](https://www.kaggle.com/datasets/bushraqurban/tourism-and-economic-impact/data) | Tourism receipts, arrivals, departures, GDP, inflation and unemployment by country and year |
| E-commerce | [Comprehensive Synthetic E-Commerce Dataset](https://www.kaggle.com/datasets/imranalishahh/comprehensive-synthetic-e-commerce-dataset) | Sales transactions with product category, revenue, discounts and ad metrics (clicks, impressions, CTR, CPC, spend) |

## Method

1. **Data cleaning and EDA:** handled missing values, duplicates and outliers, then looked at distributions, trends and correlations.
2. **Time-series forecasting:** ARIMA and Prophet to project future revenue and receipts.
3. **Machine learning regression:** Random Forest, Gradient Boosting and a Neural Network to predict revenue.
4. **Classification:** the same three models used to label periods as high or low revenue.
5. **Evaluation:** RMSE, MAE and MAPE for regression and accuracy for classification.

**Tools:** Python (pandas, scikit-learn, statsmodels, Prophet, Matplotlib, Seaborn)

## Results

### Regression (lower is better)

| Model | E-commerce RMSE | E-commerce MAPE | Tourism MAPE |
|---|---|---|---|
| Random Forest | 398.73 | 18.99% | **10.87%** |
| Gradient Boosting | **393.31** | **18.33%** | 42.50% |
| Neural Network | 399.04 | 18.43% | higher error |

### Classification (high vs low revenue)

| Model | E-commerce accuracy | Tourism accuracy |
|---|---|---|
| Random Forest | 55.21% | 98.10% |
| Gradient Boosting | 53.66% | 96.98% |
| Neural Network | 51.07% | 96.98% |

### Key findings

- **Tree-based models beat the Neural Network in both sectors.** Gradient Boosting was best for e-commerce sales and Random Forest was best for tourism receipts.
- **Tourism is harder to forecast in absolute terms.** Receipts are highly skewed with big seasonal spikes and shocks such as 2020, so absolute errors stayed large even when the percentage error was reasonable.
- **Discounts showed almost no link to e-commerce revenue** (correlation -0.10), while the ad metrics were strongly linked to each other (0.66).
- **Conversion rate rose with clicks (0.32) but fell with impressions (-0.51).** This suggests that well-targeted traffic matters more than reach.
- **Tourism receipts moved with GDP (0.45) and arrivals (0.43).**

## Limitations

- The e-commerce dataset is synthetic, which limits how much real customer behaviour it captures. The weak classification accuracy (about 55%) reflects this.
- Tourism data has few observations per country and large shocks, which makes long-range forecasts uncertain.

## Repository structure

```
tourism_ecommerce_forecasting.ipynb   all code: cleaning, EDA, forecasting and ML models
synthetic_ecommerce_data.csv          e-commerce dataset
world_tourism_economy_data.csv        tourism dataset
requirements.txt                      Python packages needed
```

## How to run

1. Download or clone this repository.
2. Install the packages: `pip install -r requirements.txt`
3. Open `tourism_ecommerce_forecasting.ipynb` in Jupyter or Google Colab and run the cells from top to bottom.

## Contact

Moin Raza | [LinkedIn](https://linkedin.com/in/md-moin-raza061254247)
