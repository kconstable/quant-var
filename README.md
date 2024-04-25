# Value-at-Risk | Conditional Value-at-Risk for a Portfolio (Historic vs Monte Carlo Simulation)

This project introduces and compares two key risk measures in finance: Value-at-Risk (VaR) and Conditional Value-at-Risk (CVaR). VaR estimates the maximum potential loss of an investment portfolio at a specified confidence level, while CVaR, or Expected Shortfall, extends this by measuring the average loss beyond the VaR threshold. 

In addition to comparing VaR and CVaR, this project also explores two methods of VaR calculation: historical VaR (HVaR) and simulation VaR (SVaR). HVaR relies on historical data to estimate potential losses, providing simplicity and transparency but may not capture changing market conditions. SVaR, on the other hand, employs a Monte Carlo simulation technique, offering flexibility and the ability to account for complex market dynamics, though it requires more computational resources and assumptions. In practice, both methods are often used in tandem.


## Securities
The AlphaVantage API was used to collect historical prices for three ETFs.  The historic VaR and CVaR were calculated based on the daily returns of the closing prices for each security.  The VaR line represents the maximum daily loss you can expect is you held that security with 95% confidence.  The CVaR represents the weight average loss beyond that threshold. This is sometimes referred to as shortfall or tail risk.
![image](https://github.com/kconstable/quant-var/assets/1649676/7087edac-bd6d-4541-a4e3-f71e6e795309)
![image](https://github.com/kconstable/quant-var/assets/1649676/f14b5fbf-eb79-4af3-b1ff-16327dc6834b)
![image](https://github.com/kconstable/quant-var/assets/1649676/2d5a47f1-aa2e-4ee0-bd8f-00e54ca53254)


## Portfolio
A hypothetical portfolio consisting of the three securities equally weighted with an initial value of $100,000.  The weights and returns of each security were used to calculate daily portfolio values and returns.  The portfolio returns were then used to calculate the historic VaR and CVaR. 

![image](https://github.com/kconstable/quant-var/assets/1649676/a4427ead-6f63-4c25-ae43-26fe7317532f)



## Monte Carlo Simulation Results

The SVaR and SCVaR were calculated using a Monte Carlo method. This methodology simulates returns for each security based on their historic mean returns, volatility, and correlations for a given time horizon. In this case, we used 255 days (approximately 1 year of trading).  For each simulation, the total return, annual return, annual volatility, and value-at-risk measures were calculated and stored.  The simulated value-at-risk measure was then calculated from the distribution of each metric.   The first plot shows the portfolio value over the period for each simulation.  The second plot shows the distribution of value-at-risk measures across all simulations.  The mean values of each can then be compared to the historical values. 

![image](https://github.com/kconstable/quant-var/assets/1649676/4b236089-d0ff-436b-a0c7-0c79c91e9042)
