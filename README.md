# Stock Price Prediction using Optimal Stopping Theory

[Code](Stock_Price_Prediction_OST.ipynb) and [Report](Report.pdf) for ASP Project 

Group Members:
- Pranav Saxena (2022AAPS0257G)
- Shrirang Bhale (2023B4A30935G)

## Prediction using Optimal Stopping Theory

Our main code which utilizes Optimal Stopping Theory can be found [here](Stock_Price_Prediction_OST.ipynb)

Results :- 

![Actual vs Prediction](assets/image.png)

The results we found seem to be accurate, with our simulated Geometric Brownian Motion (GBM) giving a good match to the actual historical data.

Backtesting Results :-
```
Initial Balance : 10000
Mean Final Balance: 9312.50
Mean Return on Investment (ROI): -6.87%
```
The predicted value of the mean ROI appears to be accurate, as the recent trend of the HAL stock has been negative, which would ultimately result in a loss, leading to a negative ROI.


We also tested the calculation of probability of reaching a target price within a specific time using P[Ta<t] = 2P(z > |a|/sqrt(t))
```
Current Price : 2287.0
Probability of reaching price 2500 in 36.00 days: 0.2133
```
The probability appears to be accurate, as the current stock trend is negative. This results in a having a lower probability of 0.2133 to get a better return.
## Extension to LSTM

We extend our method to using LSTM for comparison. [Code](OST_LSTM.ipynb)

![LSTM](assets/lstm.png)

We can see that the predicted values using LSTM are more accurate compared to simulations using Geometric Brownian Motion.

We can then predict future values of stock using our trained LSTM model and make our decisions related to trading stocks accordingly

![Future LSTM](assets/future_lstm.png)

## Conclusion

Optimal Stopping Theory (OST) can be effectively applied to stock price prediction to determine the best time to enter or exit the market, optimizing profits by deciding when to 'stop' based on predicted price movements.

For enhanced accuracy in predicting stock prices, Long Short-Term Memory (LSTM) models can be trained on historical stock data to capture long-term dependencies in price trends. Combining the predictions from LSTMs with OST can help in making informed trading decisions by identifying the optimal points to trade.

Currently, we calculate μ and σ using log returns of stock data. However, we could further refine these estimates by employing statistical techniques like Maximum Likelihood Estimation (MLE) or GARCH models. These methods could provide more accurate estimates of μ and σ, improving the application of OST for better trading accuracy.
