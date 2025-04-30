
> Name

多层级RSI回归交易策略与动态波动率调整-Multi-Level-RSI-Mean-Reversion-Strategy-with-Dynamic-Volatility-Adjustment

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/160ec169202ec0d0a4c.png)

[trans]
#### 概述

这个策略是一个基于RSI指标和价格波动性的多层级均值回归交易系统。它利用RSI的极端值和异常大的价格波动作为入场信号,同时采用金字塔式加仓和动态止盈来管理风险和优化收益。该策略的核心思想是在市场出现极端波动时入场,并在价格回归正常水平时获利了结。

#### 策略原理

1. 入场条件:
   - 使用20周期RSI(RSI20)作为主要指标
   - 设置多个RSI阈值(35/65, 30/70, 25/75, 20/80)和相应的波动率阈值
   - 当RSI达到某个阈值,且当前K线实体大小超过对应的波动率阈值时,触发入场信号
   - 额外条件:价格需要突破最近的高点/低点支撑位一定百分比

2. 加仓机制:
   - 最多允许5次入场(初始入场+4次加仓)
   - 每次加仓需满足更严格的RSI和波动率条件

3. 出场机制:
   - 设置5个不同级别的止盈点
   - 止盈点基于入场时的支撑/阻力位动态计算
   - 随着持仓数量增加,止盈目标逐渐降低

4. 风险控制:
   - 使用百分比风险模型,每次交易风险固定为账户总值的20%
   - 设置最大允许同时持仓数为5,限制总体风险敞口

#### 策略优势

1. 多层级入场:通过设置多个RSI和波动率阈值,策略可以捕捉不同程度的市场极端情况,提高交易机会。

2. 动态止盈:基于支撑/阻力位计算的止盈点,能够根据市场结构自适应调整,既保护利润又不过早离场。

3. 金字塔式加仓:在趋势延续时增加持仓,可以显著提高盈利潜力。

4. 风险管理:固定百分比风险和最大持仓限制,有效控制每笔交易和总体风险。

5. 灵活性:大量可调参数使策略能够适应不同市场环境和交易品种。

6. 均值回归+趋势跟踪:结合了均值回归和趋势跟踪的优点,既能捕捉短期反转又不错过大趋势。

#### 策略风险

1. 过度交易:在高波动市场中可能频繁触发交易信号,导致手续费过高。

2. 假突破:市场可能出现短暂的极端波动后快速回调,造成错误信号。

3. 连续亏损:如果市场持续单向运动,可能导致多次加仓后大幅亏损。

4. 参数敏感性:策略表现可能对参数设置高度敏感,存在过拟合风险。

5. 滑点影响:在剧烈波动时期,可能面临严重滑点,影响策略表现。

6. 市场环境依赖:策略在某些市场环境下可能表现欠佳,如低波动或强势趋势市场。

#### 策略优化方向

1. 动态参数调整:引入自适应机制,根据市场状态动态调整RSI和波动率阈值。

2. 多时间周期分析:结合更长期的市场趋势判断,提高入场质量。

3. 止损优化:增加追踪止损或基于ATR的动态止损,进一步控制风险。

4. 市场状态过滤:加入趋势强度、波动率周期等过滤条件,避免在不适合的市场环境交易。

5. 资金管理优化:实现更细致的仓位管理,如根据不同级别的信号调整交易规模。

6. 机器学习集成:利用机器学习算法优化参数选择和信号生成过程。

7. 相关性分析:加入与其他资产的相关性分析,提高策略的稳定性和多样性。

#### 总结

该多层级RSI回归交易策略是一个精心设计的量化交易系统,它巧妙地结合了技术分析、动态风险管理和金字塔式加仓技术。通过捕捉市场的极端波动并在价格回归时获利,策略展现了较强的盈利潜力。然而,它也面临过度交易和市场环境依赖等挑战。未来的优化方向应focus于提高策略的自适应能力和风险控制能力,以适应不同的市场环境。总的来说,这是一个具有良好基础的策略框架,通过进一步优化和回测,有望发展成为一个稳健的交易系统。

|| 

#### Overview

This strategy is a multi-level mean reversion trading system based on the RSI indicator and price volatility. It uses extreme RSI values and abnormally large price fluctuations as entry signals, while employing pyramid-style position scaling and dynamic take-profit levels to manage risk and optimize returns. The core idea of this strategy is to enter the market during extreme volatility and profit when prices return to normal levels.

#### Strategy Principles

1. Entry Conditions:
   - Uses 20-period RSI (RSI20) as the main indicator
   - Sets multiple RSI thresholds (35/65, 30/70, 25/75, 20/80) with corresponding volatility thresholds
   - Triggers entry signal when RSI reaches a threshold and current candle body size exceeds the corresponding volatility threshold
   - Additional condition: price must break through the recent high/low support level by a certain percentage

2. Position Scaling Mechanism:
   - Allows up to 5 entries (initial entry + 4 additional entries)
   - Each additional entry requires meeting stricter RSI and volatility conditions

3. Exit Mechanism:
   - Sets 5 different levels of take-profit points
   - Take-profit points are dynamically calculated based on support/resistance levels at entry
   - Take-profit targets gradually decrease as the number of open positions increases

4. Risk Control:
   - Uses a percentage risk model, with each trade risking a fixed 20% of the account value
   - Sets a maximum allowed simultaneous open positions to 5, limiting overall risk exposure

#### Strategy Advantages

1. Multi-level Entry: By setting multiple RSI and volatility thresholds, the strategy can capture different degrees of market extremes, increasing trading opportunities.

2. Dynamic Take-Profit: Take-profit points calculated based on support/resistance levels can self-adapt to market structure, protecting profits without exiting too early.

3. Pyramid-style Position Scaling: Increasing positions as trends continue can significantly enhance profit potential.

4. Risk Management: Fixed percentage risk and maximum position limits effectively control risk for each trade and overall.

5. Flexibility: Numerous adjustable parameters allow the strategy to adapt to different market environments and trading instruments.

6. Mean Reversion + Trend Following: Combines advantages of mean reversion and trend following, capturing short-term reversals without missing major trends.

#### Strategy Risks

1. Overtrading: May trigger frequent trade signals in highly volatile markets, leading to excessive fees.

2. False Breakouts: Markets may experience brief extreme volatility followed by quick reversals, causing false signals.

3. Consecutive Losses: Continuous unidirectional market movements may result in significant losses after multiple position increases.

4. Parameter Sensitivity: Strategy performance may be highly sensitive to parameter settings, risking overfitting.

5. Slippage Impact: May face severe slippage during periods of intense volatility, affecting strategy performance.

6. Market Environment Dependence: Strategy may underperform in certain market environments, such as low volatility or strong trend markets.

#### Strategy Optimization Directions

1. Dynamic Parameter Adjustment: Introduce adaptive mechanisms to dynamically adjust RSI and volatility thresholds based on market conditions.

2. Multi-timeframe Analysis: Incorporate longer-term market trend judgments to improve entry quality.

3. Stop-Loss Optimization: Add trailing stop-losses or ATR-based dynamic stop-losses for further risk control.

4. Market State Filtering: Include trend strength, volatility cycle, and other filtering conditions to avoid trading in unsuitable market environments.

5. Capital Management Optimization: Implement more detailed position management, such as adjusting trade size based on different signal levels.

6. Machine Learning Integration: Utilize machine learning algorithms to optimize parameter selection and signal generation processes.

7. Correlation Analysis: Incorporate correlation analysis with other assets to improve strategy stability and diversity.

#### Conclusion

This multi-level RSI mean reversion trading strategy is a carefully designed quantitative trading system that cleverly combines technical analysis, dynamic risk management, and pyramid-style position scaling techniques. By capturing extreme market volatility and profiting when prices revert, the strategy demonstrates strong profit potential. However, it also faces challenges such as overtrading and market environment dependence. Future optimization should focus on improving the strategy's adaptability and risk control capabilities to suit different market environments. Overall, this is a strategy framework with a solid foundation that, through further optimization and backtesting, has the potential to develop into a robust trading system.

[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-05-01 00:00:00
end: 2024-05-31 23:59:59
period: 1h
basePeriod: 15m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

//@version=5
strategy('Retorno_Pivots_5min_Novo_v3.3')

// Input variables
bars_left1 = input(1, title = "Entry - Pivot Left Bars")
bars_right1 = input(1, title = "Entry - Pivot Right Bars")
rsi20_longentry0 = input(35, title = "Entry 1 - RSI20 Long")
rsi20_shortentry0 = input(65, title = "Entry 1 - RSI20 Short")
bar_size_entry0 = input.float(1, title="Entry 1 - Bar Size")
rsi20_longentry1 = input(30, title = "Entry 2 - RSI20 Long")
rsi20_shortentry1 = input(70, title = "Entry 2 - RSI20 Short")
bar_size_entry1 = input.float(0.8, title="Entry 2 - Bar Size")
rsi20_longentry2 = input(25, title = "Entry 3 - RSI20 Long")
rsi20_shortentry2 = input(75, title = "Entry 3 - RSI20 Short")
bar_size_entry2 = input.float(0.7, title="Entry 3 - Bar Size")
rsi20_longentry3 = input(20, title = "Entry 4 - RSI20 Long")
rsi20_shortentry3 = input(80, title = "Entry 4 - RSI20 Short")
bar_size_entry3 = input.float(0.5, title="Entry 4 - Bar Size")
limit_perc1 = input.float(0.60, title="Profit Range 1")
limit_perc2 = input.float(0.40, title="Profit Range 2")
limit_perc3 = input.float(0.20, title="Profit Range 3")
limit_perc4 = input.float(0.00, title="Profit Range 4")
limit_perc5 = input.float(0.00, title="Profit Range 5")
minimum_pivot_distance = input.float(0, title="Minimum Pivot Distance %")
barsize_1h_input = input(288, title="Highest Bar Lookback")
rsi20 = ta.rsi(close, 20)
rsi200 = ta.rsi(close, 200)
Pivot_High_Last1 = ta.valuewhen(ta.pivothigh(high, bars_left1, bars_right1), ta.pivothigh(high, bars_left1, bars_right1), 0)
Pivot_Low_Last1 = ta.valuewhen(ta.pivotlow(low, bars_left1, bars_right1), ta.pivotlow(low, bars_left1, bars_right1), 0)

barsize = math.abs(close - open)
barsize_1h = ta.highest(barsize, barsize_1h_input)

Bar0Long = rsi20 < rsi20_longentry0 and barsize >= (barsize_1h * bar_size_entry0)
Bar1Long = rsi20 < rsi20_longentry1 and barsize >= (barsize_1h * bar_size_entry1)
Bar2Long = rsi20 < rsi20_longentry2 and barsize >= (barsize_1h * bar_size_entry2)
Bar3Long = rsi20 < rsi20_longentry3 and barsize >= (barsize_1h * bar_size_entry3)

// Long Entries
Long_Entry1 = strategy.opentrades == 0 and rsi20 < rsi20[1] and ((rsi20 < rsi20_longentry0 and barsize >= (barsize_1h * bar_size_entry0)) or (rsi20 < rsi20_longentry1 and barsize >= (barsize_1h * bar_size_entry1)) or (rsi20 < rsi20_longentry2 and barsize >= (barsize_1h * bar_size_entry2)) or (rsi20 < rsi20_longentry3 and barsize >= (barsize_1h * bar_size_entry3))) and close < (Pivot_Low_Last1 * (1 - (minimum_pivot_distance / 100)))
Long_Entry2 = strategy.opentrades == 1 and strategy.position_size > 0 and rsi20 < rsi20[1] and (Bar0Long or Bar1Long or Bar2Long or Bar3Long)
Long_Entry3 = strategy.opentrades == 2 and strategy.position_size > 0 and rsi20 < rsi20[1] and (Bar0Long or Bar1Long or Bar2Long or Bar3Long)
Long_Entry4 = strategy.opentrades == 3 and strategy.position_size > 0 and rsi20 < rsi20[1] and (Bar0Long or Bar1Long or Bar2Long or Bar3Long)
Long_Entry5 = strategy.opentrades == 4 and strategy.position_size > 0 and rsi20 < rsi20[1] and (Bar0Long or Bar1Long or Bar2Long or Bar3Long)
if Long_Entry1 or Long_Entry2 or Long_Entry3 or Long_Entry4 or Long_Entry5
    strategy.entry("Long", strategy.long, comment = "ENTER-LONG_BINANCE-FUTURES_BTCBUSD_Bot-BTC-1min_1M_970d2ee265390c27")
// Longs Exits
Long_Exit1 = strategy.opentrades == 1 and close > (strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc1))
Long_Exit2 = strategy.opentrades == 2 and close > (strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc2))
Long_Exit3 = strategy.opentrades == 3 and close > (strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc3))
Long_Exit4 = strategy.opentrades == 4 and close > (strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc4))
Long_Exit5 = strategy.opentrades == 5 and close > (strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc5))
if Long_Exit1 or Long_Exit2 or Long_Exit3 or Long_Exit4 or Long_Exit5
    strategy.close("Long", comment = "EXIT-LONG_BINANCE-FUTURES_BTCBUSD_Bot-BTC-1min_1M_970d2ee265390c27")

Bar0Short = rsi20 > rsi20_shortentry0 and barsize >= (barsize_1h * bar_size_entry0)
Bar1Short = rsi20 > rsi20_shortentry1 and barsize >= (barsize_1h * bar_size_entry1)
Bar2Short = rsi20 > rsi20_shortentry2 and barsize >= (barsize_1h * bar_size_entry2)
Bar3Short = rsi20 > rsi20_shortentry3 and barsize >= (barsize_1h * bar_size_entry3)

// Short Entries
Short_Entry1 = strategy.opentrades == 0 and rsi20 > rsi20[1] and ((rsi20 > rsi20_shortentry0 and barsize >= (barsize_1h * bar_size_entry0)) or (rsi20 > rsi20_shortentry1 and barsize >= (barsize_1h * bar_size_entry1)) or (rsi20 > rsi20_shortentry2 and barsize >= (barsize_1h * bar_size_entry2)) or (rsi20 > rsi20_shortentry2 and barsize >= (barsize_1h * bar_size_entry2))) and close > (Pivot_High_Last1 * (1 + (minimum_pivot_distance / 100)))
Short_Entry2 = strategy.opentrades == 1 and strategy.position_size < 0 and rsi20 > rsi20[1] and (Bar0Short or Bar1Short or Bar2Short or Bar3Short)
Short_Entry3 = strategy.opentrades == 2 and strategy.position_size < 0 and rsi20 > rsi20[1] and (Bar0Short or Bar1Short or Bar2Short or Bar3Short)
Short_Entry4 = strategy.opentrades == 3 and strategy.position_size < 0 and rsi20 > rsi20[1] and (Bar0Short or Bar1Short or Bar2Short or Bar3Short)
Short_Entry5 = strategy.opentrades == 4 and strategy.position_size < 0 and rsi20 > rsi20[1] and (Bar0Short or Bar1Short or Bar2Short or Bar3Short)
if Short_Entry1 or Short_Entry2 or Short_Entry3 or Short_Entry4 or Short_Entry5
    strategy.entry("Short", strategy.short, comment = "ENTER-SHORT_BINANCE-FUTURES_BTCBUSD_Bot-BTC-1min_1M_970d2ee265390c27")
// Short Exits
Short_Exit1 = strategy.opentrades == 1 and close < (strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc1))
Short_Exit2 = strategy.opentrades == 2 and close < (strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc2))
Short_Exit3 = strategy.opentrades == 3 and close < (strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc3))
Short_Exit4 = strategy.opentrades == 4 and close < (strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc4))
Short_Exit5 = strategy.opentrades == 5 and close < (strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc5))
if Short_Exit1 or Short_Exit2 or Short_Exit3 or Short_Exit4 or Short_Exit5
    strategy.close("Short", comment = "EXIT-SHORT_BINANCE-FUTURES_BTCBUSD_Bot-BTC-1min_1M_970d2ee265390c27")

// Plots
plot(rsi20, color=color.new(#fbff00, 0), linewidth=2)
plot(((strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc1))), color=color.new(#00ff2a, 0), linewidth=2)
plot(((strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc2))), color=color.new(#00ff2a, 50), linewidth=2)
plot(((strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc3))), color=color.new(#00ff2a, 80), linewidth=2)
plot(((strategy.position_avg_price + ((ta.valuewhen(strategy.opentrades == 0, Pivot_Low_Last1, 0) - (strategy.position_avg_price)) * limit_perc4))), color=color.new(#00ff2a, 100), linewidth=2)
plot((strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc1)), color=color.new(#ff0000, 0), linewidth=2)
plot((strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc2)), color=color.new(#ff0000, 50), linewidth=2)
plot((strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc3)), color=color.new(#ff0000, 80), linewidth=2)
plot((strategy.position_avg_price - ((strategy.position_avg_price - ta.valuewhen(strategy.opentrades == 0, Pivot_High_Last1, 0)) * limit_perc4)), color=color.new(#ff0000, 100), linewidth=2)
plot(strategy.position_avg_price, color=color.new(#ffc400, 0), linewidth=2)
plot(strategy.opentrades * (strategy.position_size / math.abs(strategy.position_size)), color=color.new(#ff00bb, 0), linewidth=2)
plot(((barsize / barsize_1h) * 100), color=color.new(#0000ff, 0), linewidth=2)
```

> Detail

https://www.fmz.com/strategy/454733

> Last Modified

2024-06-21 14:16:31
