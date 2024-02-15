# EfficientFrontier-PortfolioOptimization
"EfficientFrontier-PortfolioOptimization offers tools for creating optimal portfolios using historical data, focusing on risk-return trade-offs and maximizing Sharpe ratios for informed investment decisions."
This script is performing portfolio optimization using historical stock data for a set of assets. The key components of the analysis are:

**Historical Data Retrieval:** 
The script downloads adjusted closing prices for a set of assets (Apple, Coca-Cola, Disney, Exxon Mobil, JPMorgan Chase, McDonald's, Walmart) from Quandl for the period 2015-01-01 to 2017-12-31.
**Return Calculation:** 
It calculates the historical log returns of the assets, which are used for further analysis.
**Statistics Calculation:** 
It computes the mean, covariance, and correlation of the historical returns. These statistics are crucial for portfolio optimization.
**Random Portfolio Generation:**
The script generates 5000 random portfolios with different weight allocations for the assets. It calculates the expected return and standard deviation (volatility) for each portfolio and plots them to visualize the trade-off between risk and return.
**Global Minimum Variance (GMV) Portfolio:**
It calculates the weights of the GMV portfolio, which has the lowest possible risk (standard deviation) for a given set of assets. It does this both analytically (closed form) and numerically using quadratic programming.
**Maximum Return Portfolio:**
It calculates the portfolio with the highest expected return, again both analytically and numerically.
**Efficient Frontier:**
The script calculates and plots the efficient frontier, which is the set of portfolios that offer the highest return for a given level of risk or the lowest risk for a given level of return.
**Allocation Transition Matrix:**
It visualizes how the allocation of assets changes along a portion of the efficient frontier.
**Maximum Sharpe Ratio Portfolio:**
It calculates the portfolio with the highest Sharpe ratio, which is the ratio of excess return (over the risk-free rate) to standard deviation. This portfolio is considered the most efficient in terms of risk-adjusted return. It does this both analytically and numerically.

**Efficient Frontier and Candidate Portfolios Plot:**
This plot shows the trade-off between risk (volatility) and return for various portfolios, including both the randomly generated ones (blue dots) and those on the efficient frontier (green line). The portfolios along the green line are considered 'efficient' because they are expected to yield the highest return for a given level of risk. The blue dots represent a range of possible portfolios with varying degrees of risk and return that are not on the efficient frontier. In this context, an investor would ideally want to choose a portfolio on the efficient frontier, depending on their risk tolerance.

**Allocation Transition Matrix Plot:**
This stack plot shows how the asset allocations change for the portfolios along the efficient frontier. This visualization helps to see which assets are weighted more heavily in portfolios that are lower or higher on the frontier (i.e., more or less risky). It seems that as you move along the x-axis (which could represent increasing levels of expected return), the allocation shifts between different assets.

**Analysis of the Output:**

**Global Minimum Variance (GMV) Portfolio:**
The GMV portfolio is calculated to have allocations mainly in 'KO' (Coca-Cola) and 'DIS' (Disney), with some allocation in 'AAPL' (Apple) and 'MCD' (McDonald's). This portfolio has an expected standard deviation (risk) of 0.1604, which is the lowest among all generated portfolios, thus providing the least risky investment option.
**Maximum Return Portfolio:**
Both the closed-form and numerical methods yielded the same portfolio weights with a significant allocation to 'KO' (Coca-Cola) and 'JPM' (JPMorgan Chase). However, these weights include short positions (indicated by negative weights), which means borrowing shares to sell with the hope of repurchasing them at a lower price. This is a more aggressive strategy that might not be suitable for all investors.
**Sharpe Ratio:**
The calculated Sharpe ratio is negative, which indicates that the portfolio's performance is worse than the risk-free rate. This could be due to the negative expected returns for the assets during the period analyzed. A negative Sharpe ratio can suggest that the risk-free asset alone would be a better investment over the period.
**Key Takeaways:**

The period analyzed was not favorable for these assets since most expected returns are negative.
The GMV portfolio, while minimizing volatility, does not necessarily provide a positive return.
The maximum return portfolios are highly leveraged (use short-selling), which can be risky.
The Sharpe ratio indicates that none of these portfolios would have been expected to outperform a risk-free investment during this period.
Given these results, an investor should carefully consider whether to proceed with these strategies or to look for alternative investments, possibly including assets with better expected returns during the time period analyzed. It's also crucial to incorporate a broader market analysis, potentially looking at different time periods or additional asset classes for diversification.
