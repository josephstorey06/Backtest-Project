Moving-Average Trend Following Backtest

A small Python research project testing whether a simple trend following rule adds value across several asset classes, and how sensitive the result is to parameter choice.

The main finding is a negative one: the strategy did not beat buy-and-hold on this data. The project is mainly about testing an idea honestly and avoiding the common ways a backtest can mislead.

The idea

For each asset, the strategy is long when its fast moving average of price is above its slow moving average (an uptrend) and in cash otherwise. Positions are equal-weighted across assets.

Data

Daily adjusted prices from Yahoo Finance (via yfinance) for five ETFs spanning asset classes from a period of 2010 to 2025:
SPY	US - equities
EFA	- International developed equities
TLT	- Long-dated US Treasuries
GLD -	Gold
DBC	- Commodities

Limitations
Only five markets and a single simple rule. Real trend following programmes trade many more markets, including futures, and combine several lookback horizons.
No volatility-based position sizing, so volatile assets such as commodities can dominate portfolio risk.
Long/flat only (no shorting), and flat positions earn nothing rather than a cash rate.
Costs are a flat assumption and do not model slippage or market impact.
One historical period, so results may not hold in other regimes.

Possible extensions
Add more markets, ideally futures across equities, rates, currencies and commodities.
Size positions by inverse volatility so each asset contributes similar risk.
Combine several lookback windows instead of choosing one.
Allow short positions.
Use walk-forward testing in place of a single train/test split.
