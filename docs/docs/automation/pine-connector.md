---
title: Pine Connector
sidebar_position: 2
---

# Pine Connector
## Automating any TradeSearcher strategy with PineConnector

All scripts referenced on TradeSeacher are of type "Strategy" on TradingView, which mean they all have built-in alerts and can be automated on PineConnector.

### Requirements:
- A MetaTrader account 
- A device (or VPS) to run your MetaTrader instance when your strategy is live

### Getting started
1. [**Register**](https://www.pineconnector.com/?ref=tradesearcher) your account at PineConnector (14 days free trial)
2. Follow the PineConnector installation guide for [**MT4**](https://docs.pineconnector.com/metatrader-4?ref=tradesearcher) / [**MT5**](https://docs.pineconnector.com/metatrader-5?ref=tradesearcher)
3. [**Follow the implementation guide**](https://docs.pineconnector.com/no-code?ref=tradesearcher#block-7794255468764c9f8d02f75b833f5d08), starting from the **"Implementing Automated Scripts"** section to automate any strategy using PineConnector to your MT4/5 instance

## Important settings
### Close on Reverse
When receiving a new signal from TradingView, PineConnector will close all existing opposite positions related to the received signal (e.g., closing all short positions when a buy signal is received) and open a new position based on the signal.

For TradingView strategies, this behavior may not always be desirable—especially if the received signal is intended only to close the current position without opening a new one. Depending on your TradingView strategy, this setting should be configured accordingly.
1. **If your TradingView strategy is not always in a Buy/Sell position (most common case):**
Set the "Close on Reverse" setting to "Netting" in PineConnector to prevent opening a reverse position when your current position is closed. This way, if a Sell signal is received while you are already in a Buy position, your position will simply be closed without opening a new one.

2. **If your TradingView strategy is always in a position** (i.e., it opens a Sell position immediately after closing a Buy position):
Set the "Close on Reverse" setting to "Hedging" in PineConnector. This way, when a Sell signal is received, the current Buy position will be closed, and a new Sell position will be opened.

[**How to configure Settings on PineConnector**](https://docs.pineconnector.com/ea#block-b27ad7cecf184fa798aac54fd0c664b7)


## Before going live

### Paper Trading Before Live Trading
To insure that the signals sent are aligned with what's shown on your chart, we recommend automating your strategies to a paper trading account first to check the performance and the accuracy of the signals sent.

### Verify for strategies with Multiple Entries
Some strategies may open multiple positions at the same time, be wary of the maximum number of position that can be opened and size accordingly if necessary.
You may want to secure this setting by configurating the [**Pyramiding**](https://docs.pineconnector.com/ea#block-ff440e153f8c432684d03e1c01a6fb9e) setting on PineConnector

### Activating the strategy when there are no active positions
We recommend activating alerts on TradingView for the first time only when your strategy has no active positions. This prevents a Sell/Buy closure signal from being misinterpreted as a new position and ensures the correct sequencing of buy and sell signals.
The only exception to this rule is if your strategy is always in a position.