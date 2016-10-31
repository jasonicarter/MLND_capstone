
# Machine Learning Engineer Nanodegree
## Capstone Proposal

by Jason Carter

November X, 2016

## Proposal
_(approx. 2-3 pages)_

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

TODO: Add to references

http://www.investopedia.com/terms/i/investment.asp
http://bebusinessed.com/history/history-of-the-stock-market/
http://www.investopedia.com/articles/07/stock-exchange-history.asp
https://github.com/googledatalab/notebooks/blob/master/samples/TensorFlow%20Machine%20Learning%20with%20Financial%20Data%20on%20Google%20Cloud%20Platform.ipynb
https://github.com/rasbt/python-machine-learning-book

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

The problem to be solved: *Predict the future price of stock A, given the historic
price of stock A, over a time period of t.*

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
_(approximately 1-2 paragraphs)_

In this section, provide the details for a benchmark model or result that
relates to the domain, problem statement, and intended solution. Ideally, the
benchmark model or result contextualizes existing methods or known information
in the domain and problem given, which could then be objectively compared to the
solution. Describe how the benchmark model or result is measurable (can be
  measured by some metric and clearly observed) with thorough detail.

---

TODO: Elaborate

- Find similar stock mark indicator model for benchmarking
- A naive simple solution such as k-means or decision tree
- Backtesting???
- S&P 500???


- http://francescopochetti.com/stock-market-prediction-part-introduction/
- https://www.quantstart.com/articles/Backtesting-a-Forecasting-Strategy-for-the-SP500-in-Python-with-pandas
- http://www.investopedia.com/terms/b/benchmark.asp

### Evaluation Metrics
_(approx. 1-2 paragraphs)_

In this section, propose at least one evaluation metric that can be used to
quantify the performance of both the benchmark model and the solution model.
The evaluation metric(s) you propose should be appropriate given the context of
the data, the problem statement, and the intended solution. Describe how the
evaluation metric(s) are derived and provide an example of their mathematical
representations (if applicable). Complex evaluation metrics should be clearly
defined and quantifiable (can be expressed in mathematical or logical terms).

---

TODO: Research

- Precision, recall, F1-score???


Once you’re iterated on your stock predictor a few times, and it is giving
results you are happy with (say, predicted stock value 7 days out is
within +/- 5% of actual value, on average),

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

- workflow gray boxes backend (model) and frontend (ui)
- what analysis may be required - EDA chat
- which algos you may use
- visualization...loop back to gray boxes and workflow


**Before submitting your proposal, ask yourself. . .**

- Does the proposal you have written follow a well-organized structure similar
to that of the project template?
- Is each section (particularly **Solution Statement** and **Project Design**)
written in a clear, concise and specific fashion? Are there any ambiguous terms
or phrases that need clarification?
- Would the intended audience of your project be able to understand your
proposal?
- Have you properly proofread your proposal to assure there are minimal
grammatical and spelling mistakes?
- Are all the resources used for this project correctly cited and referenced?
