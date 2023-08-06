
# RL Trader Bot

This project is an algorithmic trading robot that utilizes reinforcement learning techniques to make buy or short decisions in the cryptocurrency market, focusing on Bitcoin and Ethereum. The robot analyzes historical price data, including candlestick data, and incorporates various technical indicators to inform its trading decisions.

The primary objective of this project is to implement a robust trading algorithm that can adapt and learn from market trends, aiming to maximize returns while managing risk.



## Problem Definition:
Goal: Training an Agent to Trade in the Market and Make a Profit
Challenges: Market Prediction is a Challenging Task. There are a lot of Parameters that the Agent should Consider. The environment is highly non-stationary. RL Algorithms need a lot of Data for Training
## Key Contribution:
1- Changing the Any Trade Environment to include Randomness in the environment
2- Adding Ethereum Data for Building the state
3- Using Deep Recurrent Q network for estimating Q value
## Environment:
We want to Trade Asset BTC/USDT:
There are a lot of Environments for RL Trading, such as TensorTrade, RLFinlab
And gym-Anytrade

We choose Anytrade because of
Simplicity and ease of use
## Data:
Data is directly gathered from Binance, which includes two month worth of data from BTCUSDT and ETHUSDT minute ohlc
We use the Historical OHLC of Bitcoin and Ethereum plus two Technical Indicators (MACD, RSI)

Normalization:
We used Min-max for normalization

Features:

Used Features for observation are: 'Open_x', 'High_x', 'Low_x', 'Close_x', 'Volume_x',
       'Quote Asset Volume_x', 'Number of Trades_x','Taker buy base asset volume_x', 'Taker buy quote asset volume_x','BTC_rsi', 'BTC_md', 'ETH_md', 'ETH_rsi',  'Close'


## Method:

Observations in our environment are highly time-correlated
Previous works used observation stacking to alleviate this problem
In this project, we used DRQN to handle this problem
LSTM modules are used to model temporal relation
2 linear layers and 1 LSTM layer are used
We also implemented Experience Replay for Sample efficiency 
The network is implemented using Pytorch
We used the DRQ algorithm for Agent

