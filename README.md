# online-shopper-conversion-analysis
A Python and Tableau analysis of online shopper behaviour and purchase conversion using the UCI Online Shoppers Purchasing Intention Dataset.

# From Browsing to Buying: Online Shopper Conversion Analysis

Python and Tableau analysis of online shopping sessions to identify characteristics associated with purchase conversion.

## Project Overview

Online retailers generate substantial quantities of data about customer sessions with their websites. Recognizing how session characteristics are associated with a purchase can enable the identification of patterns in the behaviour of customers and areas for investigation.

For this project, I performed an analysis on the Online Shoppers Purchasing Intention Dataset to investigate the differences between purchasing and non-purchasing sessions and determine whether session characteristics could be used to predict purchase outcome.

The analysis was performed using Python for data analysis and machine learning tasks and Tableau for interactive visualization.

## Research Question

What behavioural and contextual factors are associated with an online shopping session resulting in a purchase, and how well can such factors be used to predict purchase outcome?

### Supporting Questions

- How does conversion differ by visitor type?

- How is website engagement associated with purchase conversion?

- How does conversion differ across traffic types?

- How does conversion vary across shopping context such as month and weekend status?

- Can session behavioural and contextual variables be used to predict purchase outcome?

## Dataset

The project makes use of the Online Shoppers Purchasing Intention Dataset from the UCI Machine Learning Repository.

The dataset comprises:

- 12,330 shopping sessions

- 18 variables

- 10,422 non-purchasing sessions

- 1,908 purchasing sessions

- No missing values

The target variable is `Revenue` indicating whether a session resulted in a purchase.

Data source: UCI Machine Learning Repository – Online Shoppers Purchasing Intention Dataset.

## Tools and Technologies

- Python

- Pandas

- NumPy

- Matplotlib

- Seaborn

- SciPy

- Scikit-learn

- XGBoost

- Tableau Public

- Jupyter Notebook

## Analysis Process

The project followed this analytical process:

1. Data loading and initial inspection

2. Data quality checks

3. Exploratory data analysis

4. Visitor and traffic analysis

5. Behavioural analysis

6. Statistical testing

7. Predictive modelling

8. Model comparison

9. Classification threshold analysis

10. XGBoost feature importance analysis

11. Business insights and recommendations

12. Tableau dashboard development

## Key Findings

### 1. Product Engagement Associates with Purchase Conversion

Purchasing and non-purchasing sessions exhibited a substantial difference in product-related engagement.

| Metric | No Purchase | Purchase |

|---|---:|---:|

| Product-related pages | 28.71 | 48.21 |

| Product-related browsing time | 1,070 sec | 1,876 sec |

The amount of product-related browsing observed during purchasing sessions was substantially greater than during non-purchasing sessions.

### 2. Purchasing Sessions Have Lower Bounce and Exit Rates

| Metric | No Purchase | Purchase |

|---|---:|---:|

| Bounce rate | 2.53% | 0.51% |

| Exit rate | 4.74% | 1.96% |

The differences in bounce and exit rates between purchasing and non-purchasing sessions are substantial.

### 3. Conversion Varies by Visitor Type

The observed conversion rates were:

- New Visitor: 24.91%

- Other: 18.82%

- Returning Visitor: 13.93%

A chi-square test revealed an association between visitor type and purchase outcome, though the effect size was small.

### 4. Conversion Varies Across Traffic Types

Conversion rates varied considerably across traffic types. However, some traffic categories have very few sessions, and so the conversion rates should be considered in combination with the number of sessions per category.

### 5. Conversion Varies Across Months

The observed conversion rates varied across months from:

- February: 1.63%

- November: 25.35%

The conversion rates exhibited substantial variation across months.

### 6. Predictive Modelling Results Vary Across Models

Three classification models were compared:

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |

|---|---:|---:|---:|---:|---:|

| Logistic Regression | 0.845 | 0.481 | 0.034 | 0.064 | 0.734 |

| Random Forest | 0.849 | 0.565 | 0.102 | 0.173 | 0.749 |

| XGBoost | 0.844 | 0.483 | 0.076 | 0.131 | 0.773 |

The XGBoost model produced the highest ROC-AUC, while the Random Forest model achieved the highest precision, recall, and F1 score at the default 0.50 classification threshold.

Since purchasing sessions comprise only 15.5% of the dataset, accuracy is only one metric for assessing model performance.

### 7. Classification Threshold Impacts Model Performance

The XGBoost model was also evaluated at different probability thresholds.

At a threshold of 0.50:

- Precision: 48.3%

- Recall: 7.6%

At a threshold of 0.20:

- Precision: 31.2%

- Recall: 63.6%

This illustrates the trade-off between identifying more purchasing sessions and producing more false positive predictions.

## Tableau Dashboards

The Tableau Public dashboards provide an interactive view of the main findings from the analysis.

### Dashboard 1 — Conversion Overview

This dashboard presents:

- Overall conversion rate

- Purchasing and total sessions

- Conversion by visitor type

- Monthly conversion

- Weekday vs weekend conversion

- Interactive filters

### Dashboard 2 — Shopper Behaviour

This dashboard compares purchasing and non-purchasing sessions across:

- Product-related page views

- Product browsing time

- Bounce rate

- Exit rate

### Dashboard 3 — Traffic and Conversion

This dashboard examines the differences in conversion between traffic types, comparing both conversion rate and session volume.

## Business Recommendations

Based on the analysis, an online retailer could further investigate:

- The product browsing experience and interactions with product-related pages

- The sessions and areas of the website associated with higher exit rates

- Differences in website and marketing strategies for new and returning visitors

- The traffic types in terms of both conversion rate and session volume

- Using predictive scores to prioritize sessions with higher predicted purchase probabilities

These recommendations are intended as areas for further investigation rather than causal conclusions based on this dataset.

## Limitations

There are some limitations to this analysis.

- The dataset comprises 125 rows that are identical, but there is no session identifier to confirm whether these are duplicate sessions or simply sessions with identical recorded characteristics.

- The analysis identifies associations but does not establish any causal relationship.

- Some traffic types have very few sessions, and so the conversion rate estimates for these categories are less reliable.

- The predictive models were evaluated using a single train/test split without extensive parameter tuning.

- `PageValues` was excluded from the predictive models due to its potential target-related information, although it was included in the descriptive analysis.

## Project Files

- `Online_Shopper_Conversion_Analysis.ipynb` — Complete Python analysis and modelling notebook

- Tableau Public — Interactive dashboards

## Author

Sachintha Bulathsinhala

Master's Student | Data Analytics

This project was created as part of my data analytics portfolio to demonstrate practical skills in Python, statistical analysis, machine learning, and Tableau visualization.
