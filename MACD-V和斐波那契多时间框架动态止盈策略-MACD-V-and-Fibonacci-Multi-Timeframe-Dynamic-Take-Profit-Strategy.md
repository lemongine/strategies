
> Name

MACD-V和斐波那契多时间框架动态止盈策略-MACD-V-and-Fibonacci-Multi-Timeframe-Dynamic-Take-Profit-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/173e5a45d8d645ba166.png)

[trans]

#### 概述
该策略使用MACD-V(带ATR波动率的MACD)和斐波那契回调在多个时间框架上进行交易决策。它计算不同时间框架的MACD-V和斐波那契水平,然后根据当前价格与斐波那契水平的关系以及MACD-V的值来决定开仓和平仓。该策略旨在捕捉市场的趋势和回调,同时控制风险。

#### 策略原理
1. 计算不同时间框架(如5分钟和30分钟)的MACD-V指标,MACD-V是在MACD的基础上引入ATR波动率调整,以适应不同市场状态。
2. 在高级别时间框架(如30分钟)上计算过去一定周期(如9个周期)的最高价和最低价,然后基于这个区间计算斐波那契回调水平。
3. 根据当前收盘价与斐波那契水平的关系,以及MACD-V的值和变化方向,来判断是否满足开仓条件。例如,当价格回调到38.2%斐波那契水平附近,且MACD-V在-50到150之间向下运动时,开空仓。
4. 开仓后,使用移动止盈(trailing stop)来保护利润和控制风险。移动止盈的位置根据价格运动和策略参数动态调整。
5. 如果价格触及移动止损或固定止损水平,则平仓。

#### 优势分析
1. 策略采用多时间框架分析,可以更全面地把握市场趋势和波动。
2. MACD-V指标考虑了价格波动率,在趋势和震荡市中都能有效工作。
3. 斐波那契水平能够很好地捕捉价格的关键支撑和阻力区域,为交易决策提供参考。
4. 移动止盈可以在趋势延续时持续获利,同时在价格反转时及时平仓,控制风险。
5. 策略逻辑清晰,参数可调,适应性强。

#### 风险分析
1. 策略在震荡市中可能出现频繁交易,导致高额交易成本。
2. 依赖技术指标判断趋势,在市场出现假突破或持续震荡时,可能出现误判。
3. 固定止损位置可能无法及时应对极端行情,导致较大亏损。
4. 参数选择不当可能导致策略表现不佳。

#### 优化方向
1. 引入更多时间框架和指标,如更长周期的MA,以提高趋势判断的准确性。
2. 优化仓位管理,如根据ATR或价格区间动态调整仓位大小。
3. 针对不同市场状态,设置不同的参数组合,提高适应性。
4. 在移动止盈的基础上,引入移动止损,更好地控制下行风险。
5. 对策略进行回测和参数优化,找到最佳参数组合。

#### 总结
该策略通过多时间框架的MACD-V和斐波那契回调水平来判断趋势和开仓时机,并使用移动止盈来动态控制风险和利润。策略逻辑清晰,适应性强,但在震荡市中可能出现频繁交易和误判风险。通过引入更多指标、优化仓位管理和止损逻辑,以及进行参数优化,可以进一步提高策略的稳健性和盈利能力。

#### 感谢

这个策略中使用的MACD-v指标归功于原创者Alex Spiroglou。如需更多详情，您可以参考他的作品： [MACD-v.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4099617)
|| 


#### Overview
This strategy uses MACD-V (MACD with ATR volatility) and Fibonacci retracements to make trading decisions across multiple timeframes. It calculates MACD-V and Fibonacci levels on different timeframes, then decides whether to open or close positions based on the current price's relationship to the Fibonacci levels and the values of MACD-V. The strategy aims to capture market trends and retracements while controlling risk.

#### Strategy Principles
1. Calculate MACD-V indicator on different timeframes (e.g., 5-minute and 30-minute). MACD-V introduces ATR volatility adjustment to the standard MACD to adapt to different market conditions.
2. On a higher timeframe (e.g., 30-minute), calculate the highest high and lowest low of the past certain periods (e.g., 9 periods), then calculate Fibonacci retracement levels based on this range.
3. Determine whether to open a position based on the relationship between the current closing price and Fibonacci levels, as well as the value and direction of MACD-V. For example, when the price retraces to around the 38.2% Fibonacci level and MACD-V is moving downward between -50 and 150, open a short position.
4. After opening a position, use a trailing stop to protect profits and control risk. The trailing stop's position is dynamically adjusted based on price movement and strategy parameters.
5. If the price hits the trailing stop or fixed stop loss level, close the position.

#### Advantage Analysis
1. The strategy employs multi-timeframe analysis, providing a more comprehensive understanding of market trends and fluctuations.
2. The MACD-V indicator considers price volatility, making it effective in both trending and ranging markets.
3. Fibonacci levels can effectively capture key support and resistance areas, providing reference for trading decisions.
4. Trailing stops allow for continued profitability during trend continuation while timely closing positions during price reversals, controlling risk.
5. The strategy logic is clear, parameters are adjustable, and adaptability is strong.

#### Risk Analysis
1. The strategy may experience frequent trading in ranging markets, leading to high transaction costs.
2. Relying on technical indicators to judge trends may result in misjudgment when the market experiences false breakouts or prolonged oscillation.
3. Fixed stop loss positions may not respond timely to extreme market conditions, leading to significant losses.
4. Improper parameter selection may result in poor strategy performance.

#### Optimization Directions
1. Introduce more timeframes and indicators, such as longer-period MAs, to improve the accuracy of trend judgment.
2. Optimize position management, such as dynamically adjusting position size based on ATR or price range.
3. Set different parameter combinations for different market conditions to improve adaptability.
4. In addition to trailing stops, introduce trailing stop losses to better control downside risk.
5. Backtest and optimize parameters to find the best parameter combination.

#### Summary
This strategy uses MACD-V and Fibonacci retracement levels across multiple timeframes to determine trends and entry timing, and employs trailing stops to dynamically control risk and profit. The strategy logic is clear and adaptable, but may experience frequent trading and misjudgment risks in ranging markets. By introducing more indicators, optimizing position management and stop loss logic, and optimizing parameters, the strategy's robustness and profitability can be further improved.

#### Acknowledgment

The MACD-v indicator used in this strategy is credited to Alex Spiroglou, the original creator. For more details, you can refer to his work: [MACD-v.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4099617)
[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-03-26 00:00:00
end: 2024-04-25 00:00:00
period: 1h
basePeriod: 15m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

// This Pine Script™ code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © catikur

//@version=5
strategy("Advanced MACD-V and Fibonacci Strategy with EMA Trailing TP", overlay=true, default_qty_type = strategy.percent_of_equity, default_qty_value=1000, margin_long=1./10*50, margin_short=1./10*50, slippage=0, commission_type=strategy.commission.percent, commission_value=0.05)

// Parametreler
fast_len = input.int(12, title="Fast Length", minval=1, group="MACD-V Settings")
slow_len = input.int(26, title="Slow Length", minval=1, group="MACD-V Settings")
signal_len = input.int(9, title="Signal Smoothing", minval=1, group="MACD-V Settings")
atr_len = input.int(26, title="ATR Length", minval=1, group="MACD-V Settings")
source = input.source(close, title="Source", group="MACD-V Settings")

//ema_length = input.int(20, title="EMA Length for Trailing TP", group="Trailing TP Settings")
trailing_profit = input.float(1000, title="Trailing Profit", minval=0.01, maxval=1000000, step=0.01, group="Trailing TP Settings")
trailing_offset = input.float(30000, title="Trailing Offset", minval=0.01, maxval=1000000, step=0.01, group="Trailing TP Settings")
trailing_factor = input.float(0.01, title="Trailing Factor", minval=0.01, maxval=1000000, step=0.01, group="Trailing TP Settings")
fix_loss = input.float(20000, title="Fix Loss", minval=0.01, maxval=1000000, step=0.01, group="Trailing TP Settings")

fib_lookback = input.int(9, title="Fibonacci Lookback Periods", minval=1, group="Fibonacci Settings")

macd_tf = input.timeframe("5", title="MACD Timeframe", group="Timeframe Settings")
fib_tf = input.timeframe("30", title="Fibonacci Timeframe", group="Timeframe Settings")
//ema_tf = input.timeframe("30", title="EMA Timeframe for Trailing TP", group="Timeframe Settings")




// MACD-V Hesaplama
atr = ta.atr(atr_len)
ema_slow = ta.ema(source, slow_len)
ema_fast = ta.ema(source, fast_len)

atr_tf = request.security(syminfo.tickerid, macd_tf , atr)
ema_slow_tf = request.security(syminfo.tickerid, macd_tf , ema_slow)
ema_fast_tf = request.security(syminfo.tickerid, macd_tf , ema_fast)

macd = ( ema_fast_tf - ema_slow_tf ) / atr_tf * 100
signal = ta.ema(macd, signal_len)
hist = macd - signal
hist_prev = hist[1]

// log.info("MACD {0} ", macd)
// log.info("Signal {0} ", signal)
// log.info("Histogram {0} ", hist)
// log.info("Previous Histogram {0} ", hist_prev)

// EMA for Trailing TP
//ema_trailing_tf = ta.ema(close, ema_length)

//ema_trailing = request.security(syminfo.tickerid, ema_tf, ema_trailing_tf)

//log.info("EMA Trailing {0} ", ema_trailing)

// Fibonacci Seviyeleri

high_val_tf = ta.highest(high, fib_lookback)
low_val_tf = ta.lowest(low, fib_lookback)

h1 = request.security(syminfo.tickerid, fib_tf, high_val_tf)
l1 = request.security(syminfo.tickerid, fib_tf, low_val_tf)

fark = h1 - l1

//Low ile fark
hl236 = l1 + fark * 0.236
hl382 = l1 + fark * 0.382
hl500 = l1 + fark * 0.5
hl618 = l1 + fark * 0.618
hl786 = l1 + fark * 0.786
//High ile fark
lh236 = h1 - fark * 0.236
lh382 = h1 - fark * 0.382
lh500 = h1 - fark * 0.5
lh618 = h1 - fark * 0.618
lh786 = h1 - fark * 0.786

hbars_tf = -ta.highestbars(high, fib_lookback)
lbars_tf = -ta.lowestbars(low, fib_lookback)

hbars = request.security(syminfo.tickerid, fib_tf , hbars_tf)
lbars = request.security(syminfo.tickerid, fib_tf , lbars_tf)

fib_236 = hbars > lbars ? hl236 : lh236
fib_382 = hbars > lbars ? hl382 : lh382
fib_500 = hbars > lbars ? hl500 : lh500
fib_618 = hbars > lbars ? hl618 : lh618
fib_786 = hbars > lbars ? hl786 : lh786

// log.info("Fibo 382 {0} ", fib_382)
// log.info("Fibo 618 {0} ", fib_618)

// Keep track of the strategy's highest and lowest net profit
var highestNetProfit = 0.0
var lowestNetProfit  = 0.0

var bool sell_retracing = false
var bool sell_reversing = false
var bool buy_rebound = false
var bool buy_rallying = false

// Satış Koşulları
sell_retracing := (signal > -20) and (macd > -50 and macd < 150) and (macd < signal) and (hist < hist_prev) and (close < fib_382)
sell_reversing := (macd > -150 and macd < -50) and (macd < signal) and (hist < hist_prev) and (close < fib_618)

// log.info("Retracing var mi: {0} ", sell_retracing)
// log.info("Reversing var mi: {0} ", sell_reversing)

// Alım Koşulları
buy_rebound := (signal < 20) and (macd > -150 and macd < 50) and (macd > signal) and (hist > hist_prev) and ((fib_618 < close) or ((fib_618 > close ) and (close > fib_382)))
buy_rallying := (macd > 50 and macd < 150) and (macd > signal) and (hist > hist_prev) and (close > fib_618)

// log.info("Rallying var mi: {0} ", buy_rallying)
// log.info("Rebound var mi: {0} ", buy_rebound)

// Emirleri Yerleştirme
if (sell_retracing == true and strategy.opentrades == 0 )
    strategy.entry("sell_retracing", strategy.short)

if (sell_reversing == true and strategy.opentrades == 0 )
    strategy.entry("sell_reversing", strategy.short)

if (buy_rebound == true and strategy.opentrades == 0 )
    strategy.entry("buy_rebound", strategy.long)

if (buy_rallying == true and strategy.opentrades == 0 )
    strategy.entry("buy_rallying", strategy.long)


// log.info("open order: {0} ", strategy.opentrades )


highestNetProfit := math.max(highestNetProfit, strategy.netprofit)
lowestNetProfit  := math.min(lowestNetProfit, strategy.netprofit)




// Plot the net profit, as well as its highest and lowest value
//plot(strategy.netprofit, style=plot.style_area, title="Net profit",
//     color=strategy.netprofit > 0 ? color.green : color.red)

//plot(highestNetProfit, color=color.green, title="Highest net profit")
//plot(lowestNetProfit, color=color.red, title="Lowest net profit")

// Trailing Take Profit
//long_trailing_stop = ema_trailing * trailing_factor
//short_trailing_stop = ema_trailing / trailing_factor

//log.info("long trailing stop {0} ", long_trailing_stop)
//log.info("short trailing stop {0} ", short_trailing_stop)
//log.info("avg price {0} ", strategy.position_avg_price)
//trail_price1 = strategy.position_avg_price * (1 + trailing_factor)
//trail_price2 = strategy.position_avg_price * (1 - trailing_factor)
// log.info("position_size {0} ", strategy.position_size)

// Trailing Take Profit
var float long_trailing_stop = 0.0
var float short_trailing_stop = 0.0

//if (strategy.position_size > 0)
 //   long_trailing_stop := math.max(long_trailing_stop, close * (1 + trailing_factor))  // Yeni bir maksimum değer belirlendiğinde güncelle
//if (strategy.position_size < 0)
 //  short_trailing_stop := math.min(short_trailing_stop, close * (1 - trailing_factor))  // Yeni bir minimum değer belirlendiğinde güncelle

//log.info("long trailing {0} ", long_trailing_stop)
// log.info("trailing factor{0} ", trailing_factor)
//log.info("short trailing {0} ", short_trailing_stop)

if (strategy.position_size != 0 )
    strategy.exit("Exit Long", from_entry="buy_rebound", trail_points = trailing_profit, trail_offset = trailing_offset, loss = fix_loss)
    strategy.exit("Exit Long", from_entry="buy_rallying", trail_points = trailing_profit, trail_offset = trailing_offset, loss = fix_loss)
    strategy.exit("Exit Short", from_entry="sell_retracing", trail_points = trailing_profit, trail_offset = trailing_offset, loss = fix_loss)
    strategy.exit("Exit Short", from_entry="sell_reversing", trail_points = trailing_profit, trail_offset = trailing_offset, loss = fix_loss)
```

> Detail

https://www.fmz.com/strategy/449508

> Last Modified

2024-06-25 11:28:55
