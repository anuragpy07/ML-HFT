<!-- Banner -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=32&duration=2800&color=00C6FF&center=true&vCenter=true&width=1100&lines=%F0%9F%93%88+ML+-+HFT;High+Frequency+Trading+Framework;Machine%2FDeep+Learning+on+Level-II+Orderbook+Data;Signals%2C+HFT+Factors%2C+Models+%26+PnL+Visualization" />
</p>

## High Frequency Trading Framework with Machine/Deep Learning

In this project, we provide a framework/pipeline for high-frequency trading using machine learning and deep learning techniques. More advanced feature engineering (with depth, trade, and quote data) and models (such as pre-trained models) can be applied in this framework.

### Target
- Extract trading signals from level-II order book data
- Predict order book dynamics using machine learning and deep learning techniques

### Data
We use tick-level depth data of the SGX FTSE China A50 Index Futures (a major Asia-Pacific index future traded on the Singapore Exchange).

### Strategy Pipeline
<img src="./Graph/pipline.png" width="650">
  
### Order Book Signals
We use limit order book data to develop trading signals, including **Depth Ratio**, **Rise Ratio**, and **Order Book Imbalance (OBI)**.

<img src="./Graph/depth.png" width="650"> 
  
### Price Series

<img src="./images/best_bid_ask.png" width="750">

### Feature Engineering & HFT Factors Design
- Simple average depth ratio and OBI:

<img src="./images/depth_0915_1130.png" width="750">
<img src="./images/depth_1300_1600.png" width="750">

- Weighted average depth ratio, OBI, and rise ratio:

<img src="./images/rise_1300_1600_w.png" width="750">
 
### Model Fitting
- Basic Models:
  * RandomForestClassifier  
  * ExtraTreesClassifier  
  * AdaBoostClassifier  
  * GradientBoostingClassifier  
  * Support Vector Machines  
  * Other classifiers: Softmax, KNN, MLP, LSTM, etc.

- Hyperparameters:
  * Training window: 30 min  
  * Test window: 10 sec  
  * Prediction label: 15 min forward
   
### Performance Metrics
- Prediction accuracy:

<img src="./images/prediction.png" width="750">

- Prediction Accuracy Series:

<img src="./images/single_day_accuracy.png" width="800">

- Cross Validation Mean Accuracy:

<img src="./images/CV_result.png" width="800">

- Best Model:

<img src="./images/best_CV_result.png" width="800">

### PnL Visualization
<img src="./images/best_CV_result_all.png" width="800">
    
### Improvements

**Feature Engineering**

Other potentially useful signals:
- Volume imbalance signal  
- Trade imbalance signal  
- Technical indicators of bid and ask series (RSI, MACD, etc.)  
- WAP/WPR, weighted average price, VWAP, TWAP  
- ...

Signal generation techniques:
- Consider different weights for different levels of order book data for a particular signal  
- Consider moving averages with period _n_ (hyperparameter)  
- Consider weighted averages of signals, such as weighted average of trade imbalance and order book imbalance  
- Lasso regression, genetic programming  
- ...

**Models**

This project only provides a baseline. More advanced models are welcome:
- CNN  
- GRU/LSTM  
- XGBoost, AdaBoost, GBDT, LightGBM  
- Attention, Auto-encoder  
- TabNet  
- Pre-trained models  
- ...

**Performance Metrics**

The performance metrics are subject to amendment, including the PnL calculation, commission fee consideration, etc.
