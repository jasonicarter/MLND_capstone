
# Machine Learning Engineer Nanodegree
## Capstone Proposal

by Jason Carter

November X, 2016

## Proposal
_(approx. 2-3 pages)_

**Investment and Trading - A Stock Price Indicator**

### Domain Background
_(approx. 1-2 paragraphs)_

In this section, provide brief details on the background information of the
domain from which the project is proposed. Historical information relevant to
the project should be included. It should be clear how or why a problem in the
domain can or should be solved. Related academic research should be
appropriately cited in this section, including why that research is relevant.
Additionally, a discussion of your personal motivation for investigating a
particular problem in the domain is encouraged but not required.

___

*An investment is an asset or item that is purchased with the hope that it will
generate income or will appreciate in the future. [...] In finance, an
investment is a monetary asset purchased with the idea that the asset will
provide income in the future or will be sold at a higher price for a profit.*

This proposal will target the finance domain, specifically, the subset of stocks
and the stockmarket. Going forward, the definition of investing and trading
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

Ships that sailed to the East Indies were lost at sea, fortunes were squandered
or came across other mishaps and financiers wanted a way to mitigate their risk.
Being publicly traded allowed investors to own stocks and bonds of the East
India Company that entitled investors to a fixed percentage of the company's
profits.

Today, tens of thousands of companies are publicly traded on the stock market
around the world with millions of investors, ranging from casual individuals and
professional day traders to high speed volume traders and large hedge fund firms.

#### Profit
From 1602 to 2016, the ultimate goal of any investor is to make profit. Knowing
the future, or being able to predict which assets will appreciate or depreciate
in value over time, will also be advantageous to the owner of said investment.
Investment firms, hedge funds and  individual investor have been know to use
financial models to better understand market behavior and make profitable
investments and trades.

TODO: Examples, new articles, research papers
- roboadvisors
- research papers
- application of ML in the field

#### Personal Motivation
The world of machine learning permeates many domains and on a personal level
finance happens to be one of the more interesting areas. Machine learning can
not only help solve complicated financial problems but also can help the average
person grow their personal wealth (directly or indirectly) whom otherwise would
not have the opportunity due to current income or "social level". Whether this
be via analysis of their financial spending and budgeting or having access to
"roboadvisors" that, debatably, can have the same or better investment returns
as people who can afford to hire professional hedge fund managers, access to
this (open) data and the application of machine learning in the finance domain
can change lives.


http://www.investopedia.com/terms/i/investment.asp
http://bebusinessed.com/history/history-of-the-stock-market/
http://www.investopedia.com/articles/07/stock-exchange-history.asp
https://github.com/googledatalab/notebooks/blob/master/samples/TensorFlow%20Machine%20Learning%20with%20Financial%20Data%20on%20Google%20Cloud%20Platform.ipynb
https://github.com/rasbt/python-machine-learning-book

### Problem Statement
_(approx. 1 paragraph)_

In this section, clearly describe the problem that is to be solved. The problem
described should be well defined and should have at least one relevant potential
solution. Additionally, describe the problem thoroughly such that it is clear
that the problem is quantifiable (the problem can be expressed in mathematical
or logical terms) , measurable (the problem can be measured by some metric and
clearly observed), and replicable (the problem can be reproduced and occurs more
than once).

----

Essentially, if you exclude more advanced investing and trading techniques, such
as options or x, the main premise is to "buy low, sell high". That is, buy your
investment at a low price and hope to sell the same investment at price higher
then what you bought it for.

Problem - how to predict if you buy a stock at price x, that it will be x+y
given time t

Potential solution - supervised learning model trained on historic data to
predict, within a margin of error, the future closing price of a stock. This
knowledge would put the owner of said information in an advantageous position,
allowing him or her to invest in a company's stock increase or decrease in value.

For your core stock predictor, implement:
- A training interface that accepts a data range (start_date, end_date) and a
list of ticker symbols (e.g. GOOG, AAPL), and builds a model of stock behavior.
Your code should read the desired historical prices from the data source of your
choice.
- A query interface that accepts a list of dates and a list of ticker symbols,
and outputs the predicted stock prices for each of those stocks on the given
dates. Note that the query dates passed in must be after the training date
range, and ticker symbols must be a subset of the ones trained on.


### Datasets and Inputs
_(approx. 2-3 paragraphs)_

In this section, the dataset(s) and/or input(s) being considered for the project
should be thoroughly described, such as how they relate to the problem and why
they should be used. Information such as how the dataset or input is (was)
obtained, and the characteristics of the dataset or input, should be included
with relevant references and citations as necessary It should be clear how the
dataset(s) or input(s) will be used in the project and whether their use is
appropriate given the context of the problem.

---

About the dataset:
- The dataset

For this project, stock price indicator, the dataset to be used will be that of publicly traded companies from the Nasdaq stockmarket and NYSE (New York Stock Exchange) obtained for free from Yahoo! Finance via Python module "yahoo-finance".

- Why this dataset is being used (compared to others)

Nasdaq and NYSE because of their size, number of companies listed on both exchanges and historic data available for training.

- How it relates to the problem

In order to predict future stock prices, models would need current and historic data to to determine data behaviour over time or similar characteristics???

- How will the dataset be used

Historic stock data will be used for EDA, possibly feature engineering, model training and finally the trained model will be used to predict future stock prices.

**Dataset Characteristics**

Below you can see a sample of features, values and definitions of which may be used as dataset and inputs for this project.

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


https://en.wikipedia.org/wiki/NASDAQ

https://en.wikipedia.org/wiki/New_York_Stock_Exchange

http://www.investopedia.com/terms

### Solution Statement
_(approx. 1 paragraph)_

In this section, clearly describe a solution to the problem. The solution should be applicable to the project domain and appropriate for the dataset(s) or input(s) given. Additionally, describe the solution thoroughly such that it is clear that the solution is quantifiable (the solution can be expressed in mathematical or logical terms) , measurable (the solution can be measured by some metric and clearly observed), and replicable (the solution can be reproduced and occurs more than once).

---
TODO: clean up

For this project, your task is to build a stock price predictor that takes daily trading data over a certain date range as input, and outputs projected estimates for given query dates. Note that the inputs will contain multiple metrics, such as opening price (Open), highest price the stock traded at (High), how many stocks were traded (Volume) and closing price adjusted for stock splits and dividends (Adjusted Close); your system only needs to predict the Adjusted Close price.

You are free to choose what form your project takes (a simple script, a web app/service, Android/iOS app, etc.), and any additions/modifications you want to make to the project (e.g. suggesting what trades to make). Make sure you document your intended features in your report.

For your core stock predictor, implement:
A training interface that accepts a data range (start_date, end_date) and a list of ticker symbols (e.g. GOOG, AAPL), and builds a model of stock behavior. Your code should read the desired historical prices from the data source of your choice.
A query interface that accepts a list of dates and a list of ticker symbols, and outputs the predicted stock prices for each of those stocks on the given dates. Note that the query dates passed in must be after the training date range, and ticker symbols must be a subset of the ones trained on.

Once you’re iterated on your stock predictor a few times, and it is giving results you are happy with (say, predicted stock value 7 days out is within +/- 5% of actual value, on average), implement a more user-friendly interface that lets you specify stock(s) you are interested in and provides predictions at some pre-defined intervals.
You can extend the system to suggest good stocks to buy or sell, and when. You could also maintain a portfolio of stocks for the user to make these suggestions more concrete. Document these enhancements in your report, with diagrams, screenshots, etc.

A basic run of the core system would involve one call to the training interface, and one or more calls to the query interface. Implement a train-test cycle to measure the performance of your model. Use it to test prediction accuracy for query dates at different intervals after the training end date, e.g. the day immediately after training end date, 7 days later, 14 days, 28 days, etc.


### Benchmark Model
_(approximately 1-2 paragraphs)_

In this section, provide the details for a benchmark model or result that relates to the domain, problem statement, and intended solution. Ideally, the benchmark model or result contextualizes existing methods or known information in the domain and problem given, which could then be objectively compared to the solution. Describe how the benchmark model or result is measurable (can be measured by some metric and clearly observed) with thorough detail.

---

TODO: Elaborate

- Find similar stock mark indicator model for benchmarking
- A naive simple solution such as k-means or decision tree
- Backtesting???
- S&P 500???


http://francescopochetti.com/stock-market-prediction-part-introduction/

https://www.quantstart.com/articles/Backtesting-a-Forecasting-Strategy-for-the-SP500-in-Python-with-pandas

http://www.investopedia.com/terms/b/benchmark.asp

### Evaluation Metrics
_(approx. 1-2 paragraphs)_

In this section, propose at least one evaluation metric that can be used to quantify the performance of both the benchmark model and the solution model. The evaluation metric(s) you propose should be appropriate given the context of the data, the problem statement, and the intended solution. Describe how the evaluation metric(s) are derived and provide an example of their mathematical representations (if applicable). Complex evaluation metrics should be clearly defined and quantifiable (can be expressed in mathematical or logical terms).

---

- Precision, recall, F1-score???

### Project Design
_(approx. 1 page)_

In this final section, summarize a theoretical workflow for approaching a solution given the problem. Provide thorough discussion for what strategies you may consider employing, what analysis of the data might be required before being used, or which algorithms will be considered for your implementation. The workflow and discussion that you provide should align with the qualities of the previous sections. Additionally, you are encouraged to include small visualizations, pseudocode, or diagrams to aid in describing the project design, but it is not required. The discussion should clearly outline your intended workflow of the capstone project.

---

- workflow gray boxes backend (model) and frontend (ui)
- what analysis may be required - EDA chat
- which algos you may use
- visualization...loop back to gray boxes and workflow


**Before submitting your proposal, ask yourself. . .**

- Does the proposal you have written follow a well-organized structure similar to that of the project template?
- Is each section (particularly **Solution Statement** and **Project Design**) written in a clear, concise and specific fashion? Are there any ambiguous terms or phrases that need clarification?
- Would the intended audience of your project be able to understand your proposal?
- Have you properly proofread your proposal to assure there are minimal grammatical and spelling mistakes?
- Are all the resources used for this project correctly cited and referenced?
