# Machine Learning Trading bot predictor

Performs one machine learning algorithms to try to predict buy / sell signals for a emerging markets etf.
---


## Technologies
This was primarily built in jupyter labs, and requires:
- jupyter labs: Framework to process the data
- pandas: Python lib which handles stats and graphs
- sklearn: library used for training,scaling and classifying data

## Usage

   To run, just type `jupyter labs` in the main directory.
   
---

## Evaluation Report

I tried to do three additional classifications on the dataset. None of them had great precision or recall. Also, it seems like all of them failed toward the end of the testing period, I suspect that this is because the training period is kind of extreme (the etf drops about 30% in the bulk of the training period). 

As you can tell from the graph, the LogisticRegression and AdaBoostClassifier seemed to do well until the very where they dipped out. The DecisionTreeClassifier was really odd because it semmed reverse mirror the actual return. Perhaps I wasn't using that one correctly.


![alt text](https://github.com/jrossi237/ml_trading_bot/blob/main/strategies_graphed.png)
   
