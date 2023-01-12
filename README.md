# Option-Price-Simulation

In this project implements an option pricer using American Monte Carlo (Monte Carlo + Regression) based on the method prescribed by Longstaff and Schwartz. Another alternative is using the Heston Stochastic Volatility model.

The comparison of the prices for European and American options under different strikes with otherwise identical characteristics are also demonstrated.

Coding Rationale of American Monte Carlo

- Generate paths for underlying asset prices (def sim_stock_price_GBM)
- Simulate stock prices 
- Backward induction & Regression
- Generate cash flow matrix and stopping rule matrix
- Predictive variable (`x`): stock price (if in-the-money, S>K)
- Target variable (`y`): corresponding discounted option price
- Get conditional expectation function $E[Y|X]$
- Compare Exercise value and Continuation value to finalize cash flow matrix
-	Discount all cash flows then average over all path
