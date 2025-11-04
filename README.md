I built this program during part of my Computer Science class (Masters in Financial Engineering at Paris Dauphine - PSL University). 

100% python (french markdown)

- part 1 : Fama - French Model estimation using multiple linear regression
  
    3 initial factors (1993):
    
    - market return - risk free return
    - SML: company size (historically small stocks outperform bigger ones on risk-adjusted returns)
    - HML: Book-to-Market ratio (historically higher B/M outperform)
    
    2 additional factors (2015):
    
    - RMW: company profitability (higher profitability > better returns)(Robust m Weak)
    - CMA: investment level (high investment > lower returns) (Conservative m Aggressive)
    
    we use data for the 5 factors to train a multiple linear regression model.
    
    we test residue correlation (Bartlett test) > we reject the H0 that residues are uncorrelated > we lack some parameters to explain common variations of the returns
    
    <img width="834" height="837" alt="image" src="https://github.com/user-attachments/assets/4907c59a-f18d-4773-af90-b76b65b775cb" />

    
- part 2 : Technical Analysis strategies implementation
    
    sma, momentum, bollinger bands, mean reversion strategies
    
    we backtest them on numerous stocks (sharpe ratio, VaR, comparison with the buy and hold strategy, graphs, signals) and provide a recap document for every stock (it works on every yfinance ticker)
    
   <img width="1608" height="1125" alt="image" src="https://github.com/user-attachments/assets/6d9b55d8-19ee-4d2d-babd-5b95e8ba287c" />

    
   <img width="984" height="584" alt="image" src="https://github.com/user-attachments/assets/fe0c56c6-a7d3-4e02-be43-f72515633eb7" />


  Bollinger bands and mean reversion strategies generally exhibit negative returns with upward trending financial assets.

Among the four tested, the momentum trading strategy is the most likely to overperform the buy and hold strategy.
    
- part 3 : Donald Trump tweets sentiment analysis trading strategy
    
    we access a csv file that contains all Trump tweets (@realDonaldTrump on X) from 2009 to 2021.
    
    we proceed to data cleaning.
    
    for every tweet, we use vaderSentiment (https://github.com/cjhutto/vaderSentiment; open-source sentiment analysis tool specifically attuned to social media content) and arbitrary positive and negative thresholds to generate buy and sell signals on the stock market. 
    
    The strategy works best with volatile stocks such as TSLA.
