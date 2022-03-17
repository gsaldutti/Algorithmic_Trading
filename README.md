# Algorithmic_Trading

## Overview

This project aims at deploying a trading bot capable of trading, based on an algorithm which will execute buy and sell orders in accordance with a trading strategy

I was provided with the dataset (emerging_markets_ohlcv.csv) file which was read by python and converted into a dataframe and filtered into two columns "Close and Actual Returns" calculated by the pct function and dropna to drop the nan values, after that I generated the trading signals with short and long windows SMA values. Then with the creation of the signals 1, -1, the buy order and -1 the sell order. I calculated the Strategy Returns by multipliyng the actual returns by the signal values

![Algorithmic_trading](images/Strategy_returns.png)

Then I split the data in training and testing datsets and slicing the time period for the training datasets to 3 months, I used the SVC classifier to fit train and make predictions based on the testing data. After that, I reviewed the classification report associated with the SVC model.

# Conclusion 
The performance of the baseline trading algorithm in this 1st phase is giving me a result that the Strategy performs almost the same as the actual returns until the 3Q aproximatly of 2018. There is when the Strategy start to return better results till now.

![Algorithmic_trading](images/svm_plot.png)

# Tune the Baseline Trading Algorithm

What impact resulted from increasing or decreasing the training window?

When I modified the size of the training dataset, slicing my data in diferent time periods, I noticed that when I lowered the time period the accuracy of the predictions was lower compaired when I increased the time period obtaining the best results with a 7 month time period  

What impact resulted from increasing or decreasing either or both of the SMA windows?

After modifying multiple times the SMA windows up and down, I found that the best combo was the original one, short window 4 SMA and long window 100 SMA, giving me the best accuracy in the report and the best returns in the chart "Actual Returns VS Strategy Returns"

![Algorithmic_trading](images/7_month_plot.png)

# Evaluate a New Machine Learning Classifier
For this phase of the project, I choose the Logistic Regression classifier, after I first tried the Decision Tree Classifier. I tried both, but the best results came out from the Logistic Regression classifier

![Algorithmic_trading](images/Decision_tree_plot.png)

Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm?

This model performs better at some points in the time period but at the end it came down on the results and performs worst than my tuned trading algorithm

# Conclusion 

The performance of the tuned trading algorithm was better overall, compaired to the baseline and the Logistic Regression model

![Algorithmic_trading](images/LR_plot.png)

---

## Technologies

This setup assumes you already have conda installed.

This project leverages python 3.7 with the following packages:



---


![Algorithmic_trading](images/imports.png)



