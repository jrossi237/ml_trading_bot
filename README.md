# Machine Learning Trading bot predictor

Performs machine learning algorithms to try to predict buy / sell signals for a emerging markets etf.
---


## Technologies
This was primarily built in jupyter labs, and requires:
- jupyter labs: Framework to process the data
- pandas: Python lib which handles stats and graphs
- sklearn: library used for training,scaling and classifying data

## Usage

   To run, just type `jupyter labs` in the main directory.
   
---


## Part one runs using SVM:
### Run 1 Findings:
It seems like the predicted stategy was close to the actual returns.

![alt text](https://github.com/jrossi237/ml_trading_bot/blob/main/svm_strategy_graphed.png)


### Run 2 Findings:
 What impact resulted from increasing or decreasing either or both of the SMA windows?
- I tried tweaking the traing time to 4 months, and it made things worse.
- I tried to shorten the long window, and that also made it worse.
- I shortened the short_window, and it became a bit better.

![alt text](https://github.com/jrossi237/ml_trading_bot/blob/main/svm_strategy_graphed_run_2.png)




## Evaluation Report

I tried to do the three recommended classifications on the dataset. None of them had great precision or recall. 

- The ADA strategy had a rough patch in the middle, but ended okay. Having 100 or more n_estimators makes the rough patch in the middle better, but then it crashes at the end, similar to the way the LR strategy is currently crashing.
- The LR strategy seemed good for the most part, but then it crashed at the end. I tried tweaking different parameters for this. I found that setting class_weight="balanced" greatly improved it's results. However, i couldn't figure out how to not get it to crash at the end.
- The DecisionTreeClassifier isn't really working the way I have it set up. It seems like it is showing the inverse of what it should (it's like the Actual Results flipped up side down). I tried tweaking a bunch of different params, but I couldn't figure out how to fix this. At least the way it's currently set, it seems like it's accurately making the wrong decision. 

To conclude, none of these seem that great. Perhaps the best one is the ADA strategy for now, only because it's the least worse of the three. The LR result dip at the very end is very worrisome(how low will it go?), and it's strange that the DTC shows mirrored results of everything.

![alt text](https://github.com/jrossi237/ml_trading_bot/blob/main/strategies_graphed.png)



I also tried to tweak the training period from 3 months to 6 months. This seemed to have broke the ADA strategy, but the LR seemed to really like it a lot.

![alt text](https://github.com/jrossi237/ml_trading_bot/blob/main/strategies_graphed_run2.png)



   
