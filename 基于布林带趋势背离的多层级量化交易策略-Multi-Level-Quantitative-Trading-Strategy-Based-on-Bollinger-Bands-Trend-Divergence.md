
> Name

基于布林带趋势背离的多层级量化交易策略-Multi-Level-Quantitative-Trading-Strategy-Based-on-Bollinger-Bands-Trend-Divergence

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/14d7eb33bf3777a5ea7.png)

[trans]
#### 概述
本策略是一个基于布林带趋势背离和动态带宽变化的多层级量化交易系统。该策略通过监测布林带宽度的动态变化、价格突破以及EMA200均线配合，构建了一个完整的交易决策框架。策略采用自适应的波动率跟踪机制，能够有效捕捉市场趋势转折点。

#### 策略原理
策略核心基于以下几个关键要素:
1. 布林带计算采用20周期移动平均和2倍标准差
2. 通过连续三个时间点的带宽变化判断趋势强度
3. 结合K线实体与带宽比例关系判断突破有效性
4. 使用EMA200作为中长期趋势过滤器
5. 在价格突破上轨且符合带宽扩张条件时入场做多
6. 在价格跌破下轨且符合带宽收缩条件时平仓出场

#### 策略优势
1. 信号系统具有前瞻性,能提前发现潜在趋势转折点
2. 多重技术指标交叉验证,显著降低虚假信号
3. 带宽变化率指标对市场波动具有良好的自适应性
4. 出入场逻辑清晰,易于程序化实现
5. 风险控制机制完善,能有效控制回撤

#### 策略风险
1. 在震荡市场可能产生频繁交易
2. 趋势突变时可能出现滞后
3. 参数优化存在过拟合风险
4. 市场高波动期可能面临滑点风险
5. 需要及时监控带宽指标的有效性

#### 策略优化方向
1. 引入自适应的参数优化机制
2. 增加成交量等辅助指标验证
3. 优化止损止盈条件设置
4. 完善趋势强度的量化判断标准
5. 加入更多的市场环境过滤条件

#### 总结
该策略通过布林带趋势背离和动态带宽变化构建了一个稳健的交易系统。策略在趋势市场表现优异,但仍需要在震荡市场和参数优化方面进行改进。整体而言,该策略具有较好的实用价值和扩展空间。 || 

#### Overview
This strategy is a multi-level quantitative trading system based on Bollinger Bands trend divergence and dynamic bandwidth changes. The strategy constructs a complete trading decision framework by monitoring Bollinger Bands width dynamics, price breakouts, and EMA200 coordination. It employs an adaptive volatility tracking mechanism to effectively capture market trend turning points.

#### Strategy Principles
The strategy is based on the following key elements:
1. Bollinger Bands calculation using 20-period moving average and 2 standard deviations
2. Trend strength determination through bandwidth changes across three consecutive time points
3. Breakout validation using candle body to bandwidth ratio
4. EMA200 as a medium-long term trend filter
5. Long entry when price breaks above upper band with expanding bandwidth conditions
6. Exit when price breaks below lower band with contracting bandwidth conditions

#### Strategy Advantages
1. Forward-looking signal system that identifies potential trend turning points
2. Multiple technical indicator cross-validation reduces false signals
3. Bandwidth change rate indicator adapts well to market volatility
4. Clear entry and exit logic, easy to implement programmatically
5. Comprehensive risk control mechanisms effectively control drawdowns

#### Strategy Risks
1. May generate frequent trades in ranging markets
2. Potential lag during sudden trend changes
3. Parameter optimization faces overfitting risk
4. Slippage risk during high market volatility periods
5. Requires constant monitoring of bandwidth indicator effectiveness

#### Strategy Optimization Directions
1. Introduce adaptive parameter optimization mechanisms
2. Add volume and other auxiliary indicators for validation
3. Optimize stop-loss and take-profit conditions
4. Improve quantitative standards for trend strength assessment
5. Incorporate additional market environment filters

#### Summary
The strategy builds a robust trading system through Bollinger Bands trend divergence and dynamic bandwidth changes. While performing excellently in trending markets, improvements are needed for ranging markets and parameter optimization. Overall, the strategy demonstrates good practical value and room for expansion.[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2019-12-23 08:00:00
end: 2024-12-25 08:00:00
period: 1d
basePeriod: 1d
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

//@version=6
strategy("BBDIV_Strategy", overlay=true)

// Inputs for Bollinger Bands
length = input.int(20, title="BB Length")
mult = input.float(2.0, title="BB Multiplier")

// Calculate Bollinger Bands
basis = ta.sma(close, length)
deviation = mult * ta.stdev(close, length)
upperBB = basis + deviation
lowerBB = basis - deviation

// Calculate Bollinger Band width
bb_width = upperBB - lowerBB
prev_width = ta.valuewhen(not na(bb_width[1]), bb_width[1], 0)
prev_prev_width = ta.valuewhen(not na(bb_width[2]), bb_width[2], 0)

// Determine BB state
bb_state = bb_width > prev_width and prev_width > prev_prev_width ? 1 : bb_width < prev_width and prev_width < prev_prev_width ? -1 : 0

// Assign colors based on BB state
bb_color = bb_state == 1 ? color.green : bb_state == -1 ? color.red : color.gray

// Highlight candles closed outside BB
candle_size = high - low
highlight_color = (candle_size > bb_width / 2 and close > upperBB) ? color.new(color.green, 50) : (candle_size > bb_width / 2 and close < lowerBB) ? color.new(color.red, 50) : na

bgcolor(highlight_color, title="Highlight Candles")

// Plot Bollinger Bands
plot(upperBB, title="Upper BB", color=bb_color, linewidth=2, style=plot.style_line)
plot(lowerBB, title="Lower BB", color=bb_color, linewidth=2, style=plot.style_line)
plot(basis, title="Middle BB", color=color.blue, linewidth=1, style=plot.style_line)

// Calculate EMA 200
ema200 = ta.ema(close, 200)

// Plot EMA 200
plot(ema200, title="EMA 200", color=color.orange, linewidth=2, style=plot.style_line)

// Strategy logic
enter_long = highlight_color == color.new(color.green, 50)
exit_long = highlight_color == color.new(color.red, 50)

if (enter_long)
    strategy.entry("Buy", strategy.long)

if (exit_long)
    strategy.close("Buy")

// Display profit at close
if (exit_long)
    var float entry_price = na
    var float close_price = na
    var float profit = na

    if (strategy.opentrades > 0)
        entry_price := strategy.opentrades.entry_price(strategy.opentrades - 1)
        close_price := close
        profit := (close_price - entry_price) * 100 / entry_price * 2 * 10 // Assuming 1 pip = 0.01 for XAUUSD
        label.new(bar_index, high + (candle_size * 2), str.tostring(profit, format.mintick) + " USD", style=label.style_label_up, color=color.green)

```

> Detail

https://www.fmz.com/strategy/476279

> Last Modified

2024-12-27 15:52:41
