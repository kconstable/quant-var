# Value-at-Risk | Conditional Value-at-Risk for a Portfolio (Historic vs Monte Carlo Simulation)

This project introduces and compares two key risk measures in finance: Value-at-Risk (VaR) and Conditional Value-at-Risk (CVaR). VaR estimates the maximum potential loss of an investment portfolio at a specified confidence level, while CVaR, or Expected Shortfall, extends this by measuring the average loss beyond the VaR threshold. 

While comparing VaR and CVaR, it's important to note that both methods have their merits. Historical VaR (HVaR) is a practical choice due to its simplicity and transparency, even though it may not capture changing market conditions. On the other hand, Simulation VaR (SVaR) offers flexibility and the ability to account for complex market dynamics, albeit at the cost of more computational resources and assumptions. In practice, using both methods in tandem equips you with a comprehensive risk assessment strategy.


## Securities
The AlphaVantage API was used to collect historical prices for three ETFs. The historic VaR and CVaR were calculated based on the daily returns of the closing prices for each security. The VaR line represents the maximum daily loss you can expect if you hold that security with 95% confidence. The CVaR represents the weighted average loss beyond that threshold. This is sometimes referred to as shortfall or tail risk.
![image](https://github.com/kconstable/quant-var/assets/1649676/7087edac-bd6d-4541-a4e3-f71e6e795309)
![image](https://github.com/kconstable/quant-var/assets/1649676/f14b5fbf-eb79-4af3-b1ff-16327dc6834b)
![image](https://github.com/kconstable/quant-var/assets/1649676/2d5a47f1-aa2e-4ee0-bd8f-00e54ca53254)


## Portfolio
A hypothetical portfolio consisting of the three securities equally weighted with an initial value of $100,000 was constructed. The weights and returns of each security were used to calculate daily portfolio values and returns. The portfolio returns were then used to calculate the historic VaR and CVaR. 

![image](https://github.com/kconstable/quant-var/assets/1649676/a4427ead-6f63-4c25-ae43-26fe7317532f)



## Monte Carlo Simulation Results
The SVaR and SCVaR were calculated using a Monte Carlo method, a flexible and accurate technique widely used in finance. This methodology simulates returns for each security based on their historic mean returns, volatility, and correlations for a given time horizon. We used 255 days (approximately one year of trading) in this case. The total return, annual return, annual volatility, and value-at-risk measures were calculated and stored for each simulation. The simulated value-at-risk measure was then calculated from the distribution of each metric.   The first plot shows the portfolio value over the period for each simulation. The second plot shows the distribution of value-at-risk measures across all simulations. The mean values of each can then be compared to the historical values. 

![image](https://github.com/kconstable/quant-var/assets/1649676/4b236089-d0ff-436b-a0c7-0c79c91e9042)
