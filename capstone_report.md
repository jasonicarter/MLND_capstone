# Machine Learning Engineer Nanodegree
## Capstone Project
Joe Udacity  
December 31st, 2050

## I. Definition
_(approx. 1-2 pages)_

### Project Overview
In this section, look to provide a high-level overview of the project in layman’s terms. Questions to ask yourself when writing this section:
- _Has an overview of the project been provided, such as the problem domain, project origin, and related datasets or input data?_
- _Has enough background information been given so that an uninformed reader would understand the problem domain and following problem statement?_

---

#### Domain Background

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

**References**: [[1]](#1)

### Problem Statement
In this section, you will want to clearly define the problem that you are trying to solve, including the strategy (outline of tasks) you will use to achieve the desired solution. You should also thoroughly discuss what the intended solution will be for this problem. Questions to ask yourself when writing this section:
- _Is the problem statement clearly defined? Will the reader understand what you are expecting to solve?_
- _Have you thoroughly discussed how you will attempt to solve the problem?_
- _Is an anticipated solution clearly defined? Will the reader understand what results you are looking for?_

---

Essentially, if you exclude more advanced investing and trading techniques, such
as options or x, the main premise is to "buy low, sell high". That is, buy your
investment/stock at a low price and hope to sell the same investment, some time
in the future, at a price higher then what you bought it.

The problem to be solved: *Predict the future price of a given stock, given the
historic prices of said stock, over a time period using concepts and techniques
in technical analysis and machine learning.*


### Metrics
In this section, you will need to clearly define the metrics or calculations you will use to measure performance of a model or result in your project. These calculations and metrics should be justified based on the characteristics of the problem and problem domain. Questions to ask yourself when writing this section:
- _Are the metrics you’ve chosen to measure the performance of your models clearly discussed and defined?_
- _Have you provided reasonable justification for the metrics chosen based on the problem and solution?_

---

The benchmark model and solution model will be evaluated, when appropriate, with
the Root Mean Squared Error and R^2 score metrics.

**Root Mean Squared Error (RMSE)**

The root mean squared error or deviation measures the difference between values
predicted by the model and the values actually observed. It is considered to be
one of the most popular metrics for evaluating regression models.

$$ {RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2} $$

**R Squared (R^2)**

R Squared, the coefficient of determination, is an indication of the goodness of
fit of predicted values to the actual values.

$$ R^2 = 1 - \frac{SS_{res}}{SS_{tot}} $$

Model results will be considered satisfactory if the predicted stock value 7 days
in the future is within +/- 5% of the actual value, on average.

**References**: [[3]](#3)


## II. Analysis
_(approx. 2-4 pages)_

### Data Exploration
In this section, you will be expected to analyze the data you are using for the problem. This data can either be in the form of a dataset (or datasets), input data (or input files), or even an environment. The type of data should be thoroughly described and, if possible, have basic statistics and information presented (such as discussion of input features or defining characteristics about the input or environment). Any abnormalities or interesting qualities about the data that may need to be addressed have been identified (such as features that need to be transformed or the possibility of outliers). Questions to ask yourself when writing this section:
- _If a dataset is present for this problem, have you thoroughly discussed certain features about the dataset? Has a data sample been provided to the reader?_
- _If a dataset is present for this problem, are statistics about the dataset calculated and reported? Have any relevant results from this calculation been discussed?_
- _If a dataset is **not** present for this problem, has discussion been made about the input space or input data for your problem?_
- _Are there any abnormalities or characteristics about the input space or dataset that need to be addressed? (categorical variables, missing values, outliers, etc.)_

---

#### Datasets and Inputs

For this project, stock price indicator, the dataset to be used will be that of
publicly traded companies from the Nasdaq stock market and NYSE
(New York Stock Exchange) obtained for free from Yahoo! Finance via Python
module "yahoo-finance".

Nasdaq and NYSE because of their size, number of companies listed on both
exchanges and historic data available for training. In order to predict future
stock prices, models would need current and historic data to to determine data
behavior over time or similar characteristics.

Historic stock data will be used for EDA, feature selection and engineering,
model training and finally the trained model will be used to predict future stock
prices.

**Dataset Characteristics**

Below you can see a sample of features, values and definitions of which may be
used as dataset and inputs for this project.


Name              Value             Description
--------          --------------    ----------------
Adj_Close         35.83             the closing price that has been amended to include any
                                    distributions and corporate actions that occurred at
                                    any time prior to the next day's open
Close             35.83             the final price at which a security is traded on any given
                                    trading day
Date              2014-04-29        calendar date of the reported values
High              35.89             today's high is the highest price at which a stock traded
                                    during the course of the day
Low               34.12             today's low is the lowest price at which a stock traded
                                    during the course of the day
Open              34.37             the opening price is the price at which a security first
                                    trades upon the opening of an exchange on a given trading day
Symbol            YHOO              a stock symbol is a unique series of letters assigned to a
                                    security for trading purposes
Volume            28720000          the number of shares/contracts traded in a security
                                    during a given trading day
FullTimeEmployees 12200             Current number of full time employees
Sector            Technology        a sector is an area of the economy in which businesses share
                                    the same or a related product or service
start             1996-04-12        initial offering date at which a security is first made
                                    available for public purchase


**References**: [[2]](#2)


### Exploratory Visualization
In this section, you will need to provide some form of visualization that summarizes or extracts a relevant characteristic or feature about the data. The visualization should adequately support the data being used. Discuss why this visualization was chosen and how it is relevant. Questions to ask yourself when writing this section:
- _Have you visualized a relevant characteristic or feature about the dataset or input data?_
- _Is the visualization thoroughly analyzed and discussed?_
- _If a plot is provided, are the axes, title, and datum clearly defined?_

### Algorithms and Techniques
In this section, you will need to discuss the algorithms and techniques you intend to use for solving the problem. You should justify the use of each one based on the characteristics of the problem and the problem domain. Questions to ask yourself when writing this section:
- _Are the algorithms you will use, including any default variables/parameters in the project clearly defined?_
- _Are the techniques to be used thoroughly discussed and justified?_
- _Is it made clear how the input data or datasets will be handled by the algorithms and techniques chosen?_

### Benchmark
In this section, you will need to provide a clearly defined benchmark result or threshold for comparing across performances obtained by your solution. The reasoning behind the benchmark (in the case where it is not an established result) should be discussed. Questions to ask yourself when writing this section:
- _Has some result or value been provided that acts as a benchmark for measuring performance?_
- _Is it clear how this result or value was obtained (whether by data or by hypothesis)?_

---

#### Benchmark Model
The benchmark model will be comprised of multiple sources such as a naive random
forest model and stock-forecasting.com an online stock price indicators. Outside
of the train/test data backtesting will also be performed.

- Similar stock mark indicator model for benchmarking
-- http://www.stock-forecasting.com/Content/Data/Test.aspx
- A naive simple solution such as k-means or decision tree
- Backtesting
-- http://www.investopedia.com/terms/b/backtesting.asp
-- https://www.quantstart.com/articles/Backtesting-a-Forecasting-Strategy-for-the-SP500-in-Python-with-pandas


## III. Methodology
_(approx. 3-5 pages)_

### Data Preprocessing
In this section, all of your preprocessing steps will need to be clearly documented, if any were necessary. From the previous section, any of the abnormalities or characteristics that you identified about the dataset will be addressed and corrected here. Questions to ask yourself when writing this section:
- _If the algorithms chosen require preprocessing steps like feature selection or feature transformations, have they been properly documented?_
- _Based on the **Data Exploration** section, if there were abnormalities or characteristics that needed to be addressed, have they been properly corrected?_
- _If no preprocessing is needed, has it been made clear why?_

### Implementation
In this section, the process for which metrics, algorithms, and techniques that you implemented for the given data will need to be clearly documented. It should be abundantly clear how the implementation was carried out, and discussion should be made regarding any complications that occurred during this process. Questions to ask yourself when writing this section:
- _Is it made clear how the algorithms and techniques were implemented with the given datasets or input data?_
- _Were there any complications with the original metrics or techniques that required changing prior to acquiring a solution?_
- _Was there any part of the coding process (e.g., writing complicated functions) that should be documented?_

### Refinement
In this section, you will need to discuss the process of improvement you made upon the algorithms and techniques you used in your implementation. For example, adjusting parameters for certain models to acquire improved solutions would fall under the refinement category. Your initial and final solutions should be reported, as well as any significant intermediate results as necessary. Questions to ask yourself when writing this section:
- _Has an initial solution been found and clearly reported?_
- _Is the process of improvement clearly documented, such as what techniques were used?_
- _Are intermediate and final solutions clearly reported as the process is improved?_


## IV. Results
_(approx. 2-3 pages)_

### Model Evaluation and Validation
In this section, the final model and any supporting qualities should be evaluated in detail. It should be clear how the final model was derived and why this model was chosen. In addition, some type of analysis should be used to validate the robustness of this model and its solution, such as manipulating the input data or environment to see how the model’s solution is affected (this is called sensitivity analysis). Questions to ask yourself when writing this section:
- _Is the final model reasonable and aligning with solution expectations? Are the final parameters of the model appropriate?_
- _Has the final model been tested with various inputs to evaluate whether the model generalizes well to unseen data?_
- _Is the model robust enough for the problem? Do small perturbations (changes) in training data or the input space greatly affect the results?_
- _Can results found from the model be trusted?_

### Justification
In this section, your model’s final solution and its results should be compared to the benchmark you established earlier in the project using some type of statistical analysis. You should also justify whether these results and the solution are significant enough to have solved the problem posed in the project. Questions to ask yourself when writing this section:
- _Are the final results found stronger than the benchmark result reported earlier?_
- _Have you thoroughly analyzed and discussed the final solution?_
- _Is the final solution significant enough to have solved the problem?_


## V. Conclusion
_(approx. 1-2 pages)_

### Free-Form Visualization
In this section, you will need to provide some form of visualization that emphasizes an important quality about the project. It is much more free-form, but should reasonably support a significant result or characteristic about the problem that you want to discuss. Questions to ask yourself when writing this section:
- _Have you visualized a relevant or important quality about the problem, dataset, input data, or results?_
- _Is the visualization thoroughly analyzed and discussed?_
- _If a plot is provided, are the axes, title, and datum clearly defined?_

### Reflection
In this section, you will summarize the entire end-to-end problem solution and discuss one or two particular aspects of the project you found interesting or difficult. You are expected to reflect on the project as a whole to show that you have a firm understanding of the entire process employed in your work. Questions to ask yourself when writing this section:
- _Have you thoroughly summarized the entire process you used for this project?_
- _Were there any interesting aspects of the project?_
- _Were there any difficult aspects of the project?_
- _Does the final model and solution fit your expectations for the problem, and should it be used in a general setting to solve these types of problems?_

### Improvement
In this section, you will need to provide discussion as to how one aspect of the implementation you designed could be improved. As an example, consider ways your implementation can be made more general, and what would need to be modified. You do not need to make this improvement, but the potential solutions resulting from these changes are considered and compared/contrasted to your current solution. Questions to ask yourself when writing this section:
- _Are there further improvements that could be made on the algorithms or techniques you used in this project?_
- _Were there algorithms or techniques you researched that you did not know how to implement, but would consider using if you knew how?_
- _If you used your final solution as the new benchmark, do you think an even better solution exists?_

----


### References

##### 1
- http://www.diva-portal.org/smash/get/diva2:354463/fulltext01.pdf
- http://www.academia.edu/11692137/Analyzing_Different_Machine_Learning_Techniques_for_Stock_Market_Prediction
- http://cs229.stanford.edu/proj2015/009_report.pdf
- http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.278.6139&rep=rep1&type=pdf
- http://cs229.stanford.edu/proj2012/ShenJiangZhang-StockMarketForecastingusingMachineLearningAlgorithms.pdf

##### 2
- https://en.wikipedia.org/wiki/NASDAQ
- https://en.wikipedia.org/wiki/New_York_Stock_Exchange
- http://www.investopedia.com/terms

##### 3
- https://en.wikipedia.org/wiki/Root-mean-square_deviation
- https://en.wikipedia.org/wiki/Coefficient_of_determination
- http://scikit-learn.org/stable/modules/model_evaluation.html
- https://www.kaggle.com/wiki/RootMeanSquaredError

##### 4
- http://www.investopedia.com/terms/i/investment.asp
- http://bebusinessed.com/history/history-of-the-stock-market/
- http://www.investopedia.com/articles/07/stock-exchange-history.asp
- https://github.com/googledatalab/notebooks/blob/master/samples/TensorFlow%20Machine%20Learning%20with%20Financial%20Data%20on%20Google%20Cloud%20Platform.ipynb
- https://github.com/rasbt/python-machine-learning-book
- http://francescopochetti.com/stock-market-prediction-part-introduction/
- https://www.quantstart.com/articles/Forecasting-Financial-Time-Series-Part-1
- http://sebastianraschka.com/Articles/2014_intro_supervised_learning.html
