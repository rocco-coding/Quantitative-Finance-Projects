# Me and My Projects

## About Me

My name is Rocco, and I am currently studying on the University of Liverpool's Integrated Master's in Mathematics (G101) programme.

I am developing the mathematical, statistical, programming and analytical skills required for a future career in Quantitative Finance. This repository documents that development through a series of progressively more challenging projects.

Each project represents a question I wanted to investigate, a concept I wanted to understand, or a technical skill I wanted to develop.

The repository currently focuses on quantitative finance, portfolio theory, financial modelling, simulation and data analysis, with the ambition to expand into increasingly advanced areas over time.

More than simply displaying completed projects, this repository reflects a continuous learning process built around independent study, problem-solving, experimentation and progressively more ambitious research.
## Projects

### Project 1 — Random Portfolio Simulator

**Overview**

A simple simulation exploring how a portfolio's value changes over time when daily profit-and-loss outcomes are randomly generated.

Starting from an initial portfolio value of 100, the simulation runs over 50 days, randomly applying either a positive or negative unit change to the portfolio. The resulting portfolio path is recorded, analysed and visualised.

The purpose of the project was to introduce the basic mechanics of tracking portfolio value through time under uncertain outcomes.

**What I Learned**

- Using Python's `random` module to generate random outcomes.
- Using `for` loops and `range()` to repeat a process over a fixed number of periods.
- Storing changing portfolio values in a list.
- Updating variables iteratively as a simulation progresses.
- Using `.append()` to record each simulated portfolio value.
- Calculating maximum, minimum and final portfolio values using `max()`, `min()` and list indexing.
- Using Matplotlib to plot portfolio value over time.
- Understanding how a sequence of random gains and losses can produce a changing portfolio trajectory.
- Developing the foundations of simulation-based financial analysis.

### Project 2 — Trading Strategy Comparison

**Overview**

A simulation comparing the long-term portfolio performance of two traders with different probabilities of making profitable trades.

Trader A has a 50% chance of recording a profit on each trade, while Trader B has a 60% chance. Both traders begin with an initial portfolio value of 100 and are simulated over 100 trading periods.

The project investigates how a relatively small improvement in the probability of profitable trades can influence portfolio growth over time.

**What I Learned**

- Using Python's `random` module to generate probabilistic outcomes.
- Representing different probabilities through the values included in `random.choice()`.
- Running multiple simulations simultaneously within a single `for` loop.
- Tracking and updating two separate portfolio values.
- Comparing the highest, lowest and final values of different portfolios.
- Storing simulated portfolio histories in lists.
- Using Matplotlib to plot and compare multiple portfolio performance paths.
- Understanding how small differences in trading success rates can produce meaningful differences in long-term outcomes.
- Developing a stronger understanding of probability, uncertainty and simulated trading performance.

### Project 3: Monte Carlo Simulator

**Question:**  
What range of final outcomes are possible under simulated market conditions?

#### Overview

This project uses Monte Carlo simulation to generate multiple possible portfolio outcomes under random market conditions.

Rather than following just one portfolio path, the simulation creates **100 independent portfolios**, each starting with a value of 100 and evolving over 100 days. Each daily outcome is randomly determined as either a gain or loss of 1.

The final value of each simulated portfolio is collected and analysed to understand the range and distribution of possible outcomes.

#### What I Learned

- How Monte Carlo simulation can generate many possible investment outcomes
- How to use nested loops to simulate multiple portfolios over time
- How to collect and analyse final portfolio values
- How to calculate the highest, lowest, and average simulated outcomes
- How histograms display the frequency and distribution of possible results
- How simulations can illustrate uncertainty and variability in investment outcomes

#### Results

The simulation produced a distribution of final portfolio values after 100 days.

The histogram showed how frequently different outcomes occurred, while the highest, lowest, and average values provided a summary of the range of possible results.

#### Conclusion

This project demonstrated how Monte Carlo simulation can be used to model uncertainty by generating many possible portfolio outcomes under random market conditions.

Rather than focusing on one predicted result, the simulation highlighted the range, frequency, and variability of potential outcomes, providing an introduction to probabilistic modelling and investment uncertainty.

## Project 4: Monte Carlo Drawdown Analysis

### Overview

This project investigates the potential downside risk of simulated portfolios by measuring their maximum drawdowns over a fixed trading period.

Using Monte Carlo simulation, 100 independent portfolio paths were generated over 250 trading days. Each portfolio experienced randomly generated daily gains or losses, allowing the analysis to examine how severe portfolio declines could become under different simulated market conditions.

### Research Question

> What is the distribution of maximum drawdowns across simulated portfolio paths?

### Methodology

- Simulated 100 independent portfolios.
- Each portfolio began with an initial value of 100.
- Each portfolio was simulated over 250 trading days.
- Daily gains and losses were randomly generated using `random.choice([-1, 1])`.
- The running portfolio value was recorded for each simulated path.
- The maximum drawdown was calculated by comparing each portfolio value against its previous peak.
- The maximum drawdown for every portfolio was stored and analysed.
- A histogram was used to visualise the distribution of maximum drawdowns.

### Results

The simulation produced the following results:

- **Average maximum drawdown:** Approximately 17.24%
- **Worst maximum drawdown:** Approximately 44.55%
- **Best maximum drawdown:** Approximately 4.58%

The histogram showed that most portfolios experienced maximum drawdowns within a moderate range, while a smaller number experienced substantially larger declines.

### What I Learned

This project introduced the concept of **maximum drawdown** as a way of measuring the largest peak-to-trough decline experienced by a portfolio.

I learned how to:

- Track the running value of a portfolio over time.
- Identify the highest previous portfolio value, or peak.
- Calculate drawdown as a percentage decline from that peak.
- Determine the maximum drawdown across an entire portfolio path.
- Repeat the process across many simulated portfolios.
- Use a histogram to analyse the distribution of potential downside outcomes.
- Understand that two portfolios with similar final values can experience very different levels of risk along the way.

### Conclusion

The simulation demonstrated that portfolios can experience significantly different levels of downside risk even when they are generated under the same general market assumptions.

The average maximum drawdown was approximately 17.24%, but the worst simulated portfolio experienced a drawdown of approximately 44.55%. This highlights the importance of analysing the path of portfolio performance rather than focusing only on the final portfolio value.

Maximum drawdown is therefore an important risk-management measure because it helps quantify how severe losses could become during adverse market conditions.

## Project 5: Moving Average Strategy Backtest

### Overview

This project investigates whether a simple moving average trading strategy can outperform a passive buy-and-hold investment strategy.

Using one year of historical Apple stock data, the project applies a 50-day moving average to generate trading signals. The resulting strategy performance is then compared with the performance of holding the stock throughout the same period.

### Research Question

> Does a 50-day moving average strategy outperform a buy-and-hold strategy over the last year?

### Methodology

- Downloaded one year of historical Apple stock data using `yfinance`.
- Calculated the 50-day moving average of the closing price.
- Generated a trading signal:
  - `True` when the closing price was above the 50-day moving average.
  - `False` when the closing price was below the moving average.
- Calculated daily percentage returns using `pct_change()`.
- Multiplied the daily returns by the trading signal to produce strategy returns.
- Converted returns into growth factors using `1 + returns`.
- Used cumulative products with `cumprod()` to calculate portfolio growth over time.
- Calculated a separate cumulative buy-and-hold portfolio for comparison.
- Plotted both strategies to compare their performance visually.

### Results

Over the sample period:

- **Moving Average Strategy Return:** 49.5%
- **Buy-and-Hold Return:** 49.2%

The final portfolio values were approximately:

- **Moving Average Strategy:** 1.4949
- **Buy-and-Hold Strategy:** 1.4920

The moving average strategy therefore slightly outperformed the buy-and-hold strategy during this particular period.

### What I Learned

This project introduced the process of converting a basic trading rule into a simple backtest.

I learned how to:

- Download historical financial data using `yfinance`.
- Calculate rolling moving averages using pandas.
- Create trading signals based on relationships between prices and indicators.
- Calculate daily percentage returns.
- Apply trading signals to returns.
- Convert daily returns into cumulative portfolio growth.
- Use `cumprod()` to model compounded investment performance.
- Compare an active trading strategy against a passive benchmark.
- Understand that a strategy's performance depends heavily on the specific market period being tested.

### Conclusion

The 50-day moving average strategy slightly outperformed buy-and-hold over the selected one-year period, producing a return of approximately 49.5% compared with 49.2% for the passive strategy.

However, the difference was very small. This suggests that while the moving average strategy was marginally more profitable during this sample period, the result does not demonstrate a substantial advantage over simply holding the stock.

A more comprehensive backtest across multiple assets, longer time periods, different moving average windows, and additional performance metrics would be required to determine whether the strategy has a reliable long-term edge.











