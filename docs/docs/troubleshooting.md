---
title: Troubleshooting
sidebar_position: 10
---

# Troubleshooting

## Why are my backtesting results different on TradingView and TradeSearcher ?

There are many reasons why your backtesting results may differ between TradingView and TradeSearcher, but the most common ones are:

1. You are not using a Premium TradingView account. Regular TradingView accounts and plans inferior to Premium backtest using 10k bars while Premium plans and above backtest on 20k bars, being more accurate. If you use a lower plan than Premium, your results will be backtested on less data and can differ quite drastically. We also tick the 'Using bar magnifier' parameter on each backtest which can alter results.

2. You are using different parameters. Make sure the parameters of the strategy on TradingView inside the 'Properties' tab are the same as on TradeSearcher in Parameters tab (on the details part of the bottom of each backtest).

3. Backtest has been updated a long time ago. While we try to update backtests regularly, it is possible that the backtest has been updated a long time ago and that the strategy has been updated since then. Make sure to check the last updated date on TradeSearcher in the detail of the backtest (bottom right section).

## Are Trading Strategies on TradeSearcher repainting ?

Repainting is a term to describe trading strategies that are (intentionally or not) using future data while calculating each buy/sell signal, in other words it is cheating. It's a common issue with TradingView strategies that can be limited with some preventive techniques

The best way to actually test if a strategy is repainting is by limiting the amount of data it has access to while backtesting it.

All TradeSearcher strategies are backtested with our custom built Anti-Repainting system that analyze the strategy code and limit the amount of data it has access to while backtesting it. This way, we try to limit the obvious repainting strategies, but keep in mind that there is no perfect solution to this problem and that the TradingView backtesting system itself is not perfect. You can learn more about repainting strategies on TradingView website.