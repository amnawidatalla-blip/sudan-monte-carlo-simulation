
# Monte Carlo Stress Test: Portfolios in Sudan's War



My second Python project, a companion to my Markowitz portfolio test.

## Goal
If war conditions lasted a full year, what range of outcomes could a portfolio face? How often would it lose money, and how bad could the worst cases be?

## Data
Nine global proxy assets (gold, oil, wheat, US stocks, African stocks, and others) from Yahoo Finance, April 2023 to October 2026. Sudan's own market has too little liquid data.

## Method
1. Estimate each asset's average daily return and how the assets move together (covariance matrix) during the war.
2. Simulate 10,000 possible years (252 trading days each) by drawing random daily returns from a multivariate normal distribution.
3. Compute each portfolio's final value, probability of loss, and Value at Risk (the 5th percentile).
4. Compare the equal-weight portfolio with the Markowitz-optimal weights from my first project.

## Results
| | Optimal (pre-war weights) | Equal weight |
|---|---|---|
| Average value of 1 unit | 1.088 | 1.142 |
| Probability of loss | 22% | 13.7% |
| Worst 5% case (VaR 95%) | 0.914 | 0.940 |

## What I learned
I learned that lower volatility does not mean lower loss. The optimized portfolio had a narrower range of outcomes, but its lower average return put more simulated years below break-even (22% versus 13.7%). A loss is still a loss, so risk has to be judged by both the spread and the average, not by volatility alone.

## Limitations
- Assumes war conditions continue with the same average and covariance.
- Assumes normally distributed returns; real crises have larger shocks, so true worst cases may be worse.
- Statistics come from the same war period being simulated (not a forecast).
- Proxy assets are not Sudan's actual market.
