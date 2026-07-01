# Employee Sentiment Analysis and Flight Risk Prediction

## Project Overview

This project analyzes employee email communications to understand employee sentiment, identify engagement trends, rank employees based on monthly sentiment scores, detect potential flight risks, and build a predictive model for sentiment trends.

The analysis was performed using Python with Pandas, NLTK (VADER Sentiment Analyzer), Scikit-learn, Matplotlib, and Seaborn.

---

## Objectives

- Perform sentiment analysis on employee emails.
- Conduct exploratory data analysis (EDA).
- Calculate monthly sentiment scores for each employee.
- Rank employees based on monthly sentiment scores.
- Identify flight-risk employees using a rolling 30-day window.
- Develop a Linear Regression model to predict monthly sentiment scores.

---

## Methodology

### Sentiment Labeling
Each email was classified using the VADER Sentiment Analyzer into:

- Positive
- Neutral
- Negative

The labels were converted into numerical sentiment scores:

| Sentiment | Score |
|-----------|------:|
| Positive | +1 |
| Neutral | 0 |
| Negative | -1 |

---

### Monthly Sentiment Score

For every employee, sentiment scores were aggregated monthly.

Positive messages increased the score, negative messages reduced it, while neutral messages had no effect.

---

### Employee Ranking

For every month:

- Top 3 Positive Employees were identified based on the highest sentiment scores.
- Top 3 Negative Employees were identified based on the lowest sentiment scores.

---

### Flight Risk Identification

An employee was flagged as a Flight Risk if they sent **4 or more negative emails within any rolling 30-day period**, irrespective of calendar months.

---

### Predictive Modeling

A Linear Regression model was built using features including:

- Average message length
- Average word count
- Monthly message frequency

The target variable was the monthly sentiment score.

---

# Summary of Results

## Frequently Appearing Positive Employees

The monthly rankings consistently highlighted employees such as:

- kayne.coulter@enron.com
- john.arnold@enron.com
- lydia.delgado@enron.com
- eric.bass@enron.com
- johnny.palmer@enron.com

as strong positive contributors across multiple months.

---

## Frequently Appearing Lower-Scoring Employees

Employees that repeatedly appeared among the lowest monthly sentiment scores included:

- bobette.riner@ipgdirect.com
- johnny.palmer@enron.com
- rhonda.denton@enron.com
- don.baughman@enron.com

These rankings indicate comparatively lower monthly sentiment scores rather than consistently negative behaviour.

---

## Flight Risk Employees

The following employees met the flight-risk criteria:

- bobette.riner@ipgdirect.com
- don.baughman@enron.com
- johnny.palmer@enron.com
- sally.beck@enron.com

---

# Key Insights

- Employee communication was predominantly positive throughout the observation period.
- Positive sentiment consistently exceeded neutral and negative communications.
- Negative sentiment remained relatively low with no major organization-wide spikes.
- A small subset of employees generated repeated negative communications and were successfully identified using the rolling 30-day analysis.
- Monthly sentiment scores remained relatively stable, suggesting healthy communication patterns overall.

---

# Predictive Model

The Linear Regression model was evaluated using:

- Mean Squared Error (MSE)
- R² Score

The model achieved a relatively low predictive performance, indicating that message length and word count alone are insufficient to accurately predict employee sentiment.

Future models could incorporate:

- Email response time
- Communication network features
- Topic modeling
- Historical sentiment trends
- Recipient interactions

---

# Recommendations

- Monitor employees identified as flight risks through periodic engagement reviews.
- Incorporate additional behavioral and communication features into future predictive models.
- Continue tracking monthly sentiment to detect emerging organizational trends.
- Consider transformer-based sentiment models for improved classification accuracy.

---

## Technologies Used

- Python
- Pandas
- NumPy
- NLTK (VADER)
- Matplotlib
- Seaborn
- Scikit-learn
