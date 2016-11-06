
# Machine Learning Engineer Nanodegree
## Capstone Proposal

by Jason Carter

November X, 2016

## Proposal

**Investment and Trading - A Stock Price Indicator**

### Domain Background

*An investment is an asset or item that is purchased with the hope that it will
generate income or will appreciate in the future. [...] In finance, an
investment is a monetary asset purchased with the idea that the asset will
provide income in the future or will be sold at a higher price for a profit.*

This proposal will target the finance domain, specifically, the subset of stocks
and the stock market. Going forward, the definition of investing and trading
will be accepted as:

- **Investing** is the act of committing money or capital to an endeavor
(a business, project, real estate, etc.) with the expectation of obtaining an
additional income or profit.

- **Trading** is a basic economic concept involving the buying and selling of
goods and services, with compensation paid by a buyer to a seller, or the
exchange of goods or services between parties. [...] In financial markets,
trading refers to the buying and selling of securities, such as the purchase of
stock on the floor of the New York Stock Exchange (NYSE).

#### The First Stock Market
The world’s first stock markets are generally linked back to Antwerp, Belgium as
far back as 1531. But it wasn't until 1602, when the Dutch East India Company
officially became the world’s first publicly traded company.

Today, tens of thousands of companies are publicly traded on the stock market
around the world with millions of investors, ranging from casual individuals and
professional day traders to high speed volume traders and large hedge fund firms.

#### In Search of Profit, knowledge and Understanding
From 1602 'til now, the ultimate goal of any investor has been to make profit.
Being able to **predict** which assets will appreciate or depreciate in value over
time, is obviously advantageous to the owner of said knowledge. Whether it be
individual investors, hedge fund firms or academic researchers there has always
been interest in the stock market in search of profit, knowledge and Understanding.

#### Personal Motivation
The world of machine learning permeates many domains, and on a personal level
finance happens to be one of the more interesting areas. Machine learning can
not only help solve complicated financial problems but also can help the average
citizen grow their personal wealth (directly or indirectly) whom otherwise would
not have the opportunity due to income or social level. Whether this
be via analysis of their financial spending and budgeting or having access to
financial tool such as "roboadvisors", this data and the application of machine
learning in the finance domain can change lives.

- roboadvisors
- http://www.diva-portal.org/smash/get/diva2:354463/fulltext01.pdf
- http://www.academia.edu/11692137/Analyzing_Different_Machine_Learning_Techniques_for_Stock_Market_Prediction
- http://cs229.stanford.edu/proj2015/009_report.pdf
- http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.278.6139&rep=rep1&type=pdf
- http://cs229.stanford.edu/proj2012/ShenJiangZhang-StockMarketForecastingusingMachineLearningAlgorithms.pdf

### Problem Statement

Essentially, if you exclude more advanced investing and trading techniques, such
as options or x, the main premise is to "buy low, sell high". That is, buy your
investment/stock at a low price and hope to sell the same investment, some time
in the future, at a price higher then what you bought it.

The problem to be solved: *Predict the future price of a given stock, given the
historic prices of said stock, over a time period using concepts and techniques
in technical analysis and machine learning.*

### Datasets and Inputs

For this project, stock price indicator, the dataset to be used will be that of
publicly traded companies from the Nasdaq stock market and NYSE
(New York Stock Exchange) obtained for free from Yahoo! Finance via Python
module "yahoo-finance".

Nasdaq and NYSE because of their size, number of companies listed on both
exchanges and historic data available for training. In order to predict future
stock prices, models would need current and historic data to to determine data
behavior over time or similar characteristics???

Historic stock data will be used for EDA, feature selection and engineering,
model training and finally the trained model will be used to predict future stock
prices.

**Dataset Characteristics**

Below you can see a sample of features, values and definitions of which may be
used as dataset and inputs for this project.

Name | Value | Description
--- | --- | ---
Adj_Close | 35.83 | the closing price that has been amended to include any distributions and corporate actions that occurred at any time prior to the next day's open
Close | 35.83 | the final price at which a security is traded on any given trading day
Date | 2014-04-29 | calendar date of the reported values
High | 35.89 | today's high is the highest price at which a stock traded during the course of the day
Low | 34.12 | today's low is the lowest price at which a stock traded during the course of the day
Open | 34.37 | the opening price is the price at which a security first trades upon the opening of an exchange on a given trading day
Symbol | YHOO | a stock symbol is a unique series of letters assigned to a security for trading purposes
Volume | 28720000 | the number of shares/contracts traded in a security during a given trading day
FullTimeEmployees | 12200 | Current number of full time employees
Industry | Internet Information Providers | a classification that refers to groups of companies that are related based on their primary business activities
Sector | Technology | a sector is an area of the economy in which businesses share the same or a related product or service
start | 1996-04-12 | initial offering date at which a security is first made available for public purchase

- https://en.wikipedia.org/wiki/NASDAQ
- https://en.wikipedia.org/wiki/New_York_Stock_Exchange
- http://www.investopedia.com/terms

### Solution Statement

For this project, your task is to build a stock price predictor that takes daily
trading data over a certain date range as input, and outputs projected estimates
for given query dates.

A training interface that accepts a data range (start_date, end_date) and a
list of ticker symbols (e.g. GOOG, AAPL), and builds a model of stock behavior.
Your code should read the desired historical prices from the data source of your
choice.

A query interface that accepts a list of dates and a list of ticker symbols, and
outputs the predicted stock prices for each of those stocks on the given dates.
Note that the query dates passed in must be after the training date range, and
ticker symbols must be a subset of the ones trained on.

Potential solution - supervised learning model trained on historic data to
predict, within a margin of error, the future closing price of a stock. This
knowledge would put the owner of said information in an advantageous position,
allowing him or her to invest in a company's stock increase or decrease in value.

### Benchmark Model

- Similar stock mark indicator model for benchmarking
-- http://www.stock-forecasting.com/Content/Data/Test.aspx
- A naive simple solution such as k-means or decision tree
- Backtesting
-- http://www.investopedia.com/terms/b/backtesting.asp
-- https://www.quantstart.com/articles/Backtesting-a-Forecasting-Strategy-for-the-SP500-in-Python-with-pandas
- S&P 500 (compare to future results)
-- http://www.investopedia.com/terms/b/benchmark.asp

### Evaluation Metrics

The benchmark model and solution model will be evaluated, when appropriate, with
the Root Mean Squared Error and R^2 score metrics.

**Root Mean Squared Error (RMSE)**

The root mean squared error or deviation measures the difference between values
predicted by the model and the values actually observed. It is considered to be
one of the most popular metrics for evaluating regression models.

\[ {RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2} \]

**R Squared (R^2)**

R Squared, the coefficient of determination, is an indication of the goodness of
fit of predicted values to the actual values.

\[ R^2 = 1 - \frac{SS_{res}}{SS_{tot}} \]

Model results will be considered satisfactory if the predicted stock value 7 days
in the future is within +/- 5% of the actual value, on average.

- https://en.wikipedia.org/wiki/Root-mean-square_deviation
- https://en.wikipedia.org/wiki/Coefficient_of_determination
- http://scikit-learn.org/stable/modules/model_evaluation.html
- https://www.kaggle.com/wiki/RootMeanSquaredError

### Project Design
_(approx. 1 page)_

In this final section, summarize a theoretical workflow for approaching a
solution given the problem. Provide thorough discussion for what strategies you
may consider employing, what analysis of the data might be required before being
used, or which algorithms will be considered for your implementation. The
workflow and discussion that you provide should align with the qualities of the
previous sections. Additionally, you are encouraged to include small
visualizations, pseudocode, or diagrams to aid in describing the project design,
but it is not required. The discussion should clearly outline your intended
workflow of the capstone project.

---

Describe the project as a product, and the overall strategy which is divided
into two sections (model/backend and frontend) of the product.

The approach for this problem will, as a whole, take the view of a product and
have not just a predictive model but a user interface (UI) for someone to easily
interactive with and request predictions. Additionally, the system will provide
its own historical predictions and its final accuracy.

Below are the associated processes for both the 1) Modeling and 2) UI workflows:

#### Modeling Workflow - Supervised Learning

1. Data gathering + collection
2. Data pre-processing
..* Feature engineering, missing data
3. EDA and visualizations
4. Model evaluation / cross-validation
..* Feature reduction / selection
..* Dimensionality reduction
..* Train/test data split
..* Tuning / hyperparamater optimization
5. Final model
..* Test dataset / backtesting
6. Predictions
..* New / future data

workflow diagrams

**Data gathering and pre-processing**

Data will be sourced mainly from Yahoo Finance API via the python module
yahoo-finance 1.3.2.
- where the data is coming from
- what will you probably do with the data (CAPM?)

**EDA and visualizations**

In order to best fit and model the data, exploratory data analysis will first be
performed to understand the type of data being used and determine any particular
relationships or correlations. EDA and visualizations will take the shape of
statistical data summary, log transformations, correlation matrix, etc. Once
a handle of the data has been accomplished through analysis and graph plots
the model evaluation phase will begin.

**Model evaluation and Cross-validation**
- Talk about benchmark? use decision tree. online test.
- Cross-validation
- Metric -> +/- 5% of actual value

**Backtesting**
- Not sure yet, there's an API thing I may be able to use to validate stuff

#### UI Workflow - Flask Microframework

**Development perspective**

1. Environment setup
--* Set up Flask
2. Flask RESTful implementation
--* Create restful endpoints
3. Flask DB implementation
--* Create data storage for tracking previous predictions and results
4. Test APIs and data storage

**User perspective**

1. Visit landing page of stock price indictor
2. User enters stock symbol of stock price to predict
3. User selects a future range of prediction (e.g. 7 days from today)
4. The system will then display the stock price prediction
--* The system will also display a "prediction stock ticker" which will display
past predictions from previous user requests and the system's prediction along
with actual results

workflow diagrams

### References

- http://www.investopedia.com/terms/i/investment.asp
- http://bebusinessed.com/history/history-of-the-stock-market/
- http://www.investopedia.com/articles/07/stock-exchange-history.asp
- https://github.com/googledatalab/notebooks/blob/master/samples/TensorFlow%20Machine%20Learning%20with%20Financial%20Data%20on%20Google%20Cloud%20Platform.ipynb
- https://github.com/rasbt/python-machine-learning-book
- http://francescopochetti.com/stock-market-prediction-part-introduction/
- https://www.quantstart.com/articles/Forecasting-Financial-Time-Series-Part-1
- http://sebastianraschka.com/Articles/2014_intro_supervised_learning.html
