
> Name

双重Vegas通道波动性调整SuperTrend量化交易策略-Double-Vegas-Channel-Volatility-Adjusted-SuperTrend-Quantitative-Trading-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/bd59a73a29bda0b43c.png)

[trans]
#### 概述
"双重Vegas通道波动性调整SuperTrend量化交易策略"是一个高级的量化交易系统,结合了两个具有不同参数设置的Vegas通道波动性调整SuperTrend指标,旨在更准确地捕捉市场趋势并生成与总体市场方向一致的交易信号。该策略通过整合波动性调整和利用Vegas通道的宽度来优化SuperTrend计算,形成一个动态响应的交易系统。此外,该策略还结合了可自定义的止盈和止损水平,为风险管理提供了一个稳健的框架。

#### 策略原理
该策略首先计算Vegas通道,该通道由特定窗口长度内收盘价的简单移动平均线(SMA)和标准差(STD)派生而来。该通道有助于衡量市场波动性,并为调整SuperTrend指标奠定了基础。接下来,利用平均真实范围(ATR)和调整后的乘数确定SuperTrend的上下阈值。市场趋势通过将收盘价与SuperTrend阈值进行比较来确定。只有当两个SuperTrend指标都指向相同的市场方向时,才会生成交易信号。

#### 策略优势
"双重Vegas通道波动性调整SuperTrend量化交易策略"的主要优势在于它能够动态调整SuperTrend指标以适应不断变化的市场条件。通过整合Vegas通道宽度,该策略可以更好地应对市场波动,提高趋势识别的准确性。此外,使用两个具有不同参数设置的SuperTrend指标可以提供更全面的市场视角,有助于确认趋势并过滤掉错误信号。可自定义的止盈和止损水平进一步增强了该策略的风险管理能力。

#### 策略风险
尽管该策略旨在提高趋势识别的准确性,但仍然存在一些风险。首先,在波动性极高或市场走势不明朗的情况下,该策略可能会生成错误的交易信号。其次,过于频繁的交易可能导致高昂的交易成本,影响策略的整体表现。为了缓解这些风险,交易者可以考虑优化策略参数,如调整ATR周期、Vegas通道窗口长度和SuperTrend乘数,以适应特定的市场条件。此外,设置适当的止盈和止损水平也至关重要,以控制潜在损失。

#### 策略优化方向
"双重Vegas通道波动性调整SuperTrend量化交易策略"可以通过多种方式进行优化。一个潜在的优化方向是结合其他技术指标,如相对强弱指数(RSI)或移动平均线收敛发散(MACD),以提高趋势确认的可靠性。另一个优化方向是引入自适应机制,根据市场状况动态调整策略参数。这可以通过使用机器学习算法或基于规则的方法来实现。此外,优化持仓时间和止盈止损水平也可以提高策略的整体表现。

#### 总结
总的来说,"双重Vegas通道波动性调整SuperTrend量化交易策略"是一个强大的交易系统,通过整合波动性调整和利用Vegas通道宽度来提高趋势识别的准确性。该策略使用两个具有不同参数设置的SuperTrend指标,以获得更全面的市场视角。尽管该策略展现出了巨大的潜力,但仍需谨慎对待其固有风险。通过优化策略参数、引入其他技术指标和实施自适应机制,可以进一步提高该策略的性能。

|| 

#### Overview
The "Double Vegas Channel Volatility-Adjusted SuperTrend Quantitative Trading Strategy" is an advanced quantitative trading system that combines two Vegas Channel Volatility-Adjusted SuperTrend indicators with different parameter settings. It aims to more accurately capture market trends and generate trades that align with the overall market direction. The strategy integrates volatility adjustments and leverages the width of the Vegas Channel to optimize the SuperTrend calculations, resulting in a dynamic and responsive trading system. Additionally, the strategy incorporates customizable take-profit and stop-loss levels, providing a robust framework for risk management.

#### Strategy Principle
The strategy begins by calculating the Vegas Channel, which is derived from the simple moving average (SMA) and standard deviation (STD) of the closing prices over a specified window length. This channel helps measure market volatility and forms the basis for adjusting the SuperTrend indicator. Next, the Average True Range (ATR) and the adjusted multiplier are used to determine the upper and lower thresholds of the SuperTrend. The market trend is determined by comparing the closing prices with the SuperTrend thresholds. Trade signals are generated only when both SuperTrend indicators align in the same market direction.

#### Strategy Advantages
The main advantage of the "Double Vegas Channel Volatility-Adjusted SuperTrend Quantitative Trading Strategy" lies in its ability to dynamically adjust the SuperTrend indicator to adapt to changing market conditions. By incorporating the width of the Vegas Channel, the strategy can better respond to market volatility, improving the accuracy of trend identification. Moreover, using two SuperTrend indicators with different parameter settings provides a more comprehensive view of the market, helping to confirm trends and filter out false signals. The customizable take-profit and stop-loss levels further enhance the risk management capabilities of the strategy.

#### Strategy Risks
Although the strategy aims to improve the accuracy of trend identification, there are still some risks involved. Firstly, the strategy may generate false trading signals during periods of extremely high volatility or unclear market direction. Secondly, overly frequent trading can lead to high transaction costs, affecting the overall performance of the strategy. To mitigate these risks, traders can consider optimizing the strategy parameters, such as adjusting the ATR periods, Vegas Channel window lengths, and SuperTrend multipliers to suit specific market conditions. Additionally, setting appropriate take-profit and stop-loss levels is crucial to control potential losses.

#### Strategy Optimization Directions
The "Double Vegas Channel Volatility-Adjusted SuperTrend Quantitative Trading Strategy" can be optimized in several ways. One potential optimization direction is to incorporate additional technical indicators, such as the Relative Strength Index (RSI) or Moving Average Convergence Divergence (MACD), to enhance the reliability of trend confirmation. Another optimization direction is to introduce adaptive mechanisms that dynamically adjust the strategy parameters based on market conditions. This can be achieved using machine learning algorithms or rule-based approaches. Furthermore, optimizing the holding periods and take-profit/stop-loss levels can also improve the overall performance of the strategy.

#### Summary
In summary, the "Double Vegas Channel Volatility-Adjusted SuperTrend Quantitative Trading Strategy" is a powerful trading system that improves trend identification accuracy by integrating volatility adjustments and leveraging the width of the Vegas Channel. The strategy employs two SuperTrend indicators with different parameter settings to provide a more comprehensive market perspective. While the strategy shows great potential, its inherent risks should be approached with caution. By optimizing strategy parameters, incorporating additional technical indicators, and implementing adaptive mechanisms, the performance of the strategy can be further enhanced.

[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-05-01 00:00:00
end: 2024-05-31 23:59:59
period: 3h
basePeriod: 15m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

// This Pine Script™ code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © PresentTrading

// The "Double Vegas SuperTrend Enhanced" strategy uses two SuperTrend indicators with different ATR and Vegas Channel settings 
// to identify market trends and generate trades. Trades are executed only when both SuperTrends align in the same direction. 
// The strategy includes configurable take-profit and stop-loss levels, and plots the SuperTrend levels on the chart.

//@version=5
strategy("Double Vegas SuperTrend Enhanced - Strategy [presentTrading]", shorttitle="Double Vegas SuperTrend Enhanced - Strategy [presentTrading]", overlay=true, overlay = false, 
 precision=3, commission_value= 0.1, commission_type=strategy.commission.percent, slippage= 1, currency=currency.USD, default_qty_type = strategy.percent_of_equity, 
 default_qty_value = 10, initial_capital= 10000)


// Input settings allow the user to customize the strategy's parameters.
tradeDirectionChoice = input.string(title="Trade Direction", defval="Both", options=["Long", "Short", "Both"]) // Option to select the trading direction

// Settings for the first Vegas SuperTrend
atrPeriod1 = input(10, "ATR Period for SuperTrend 1") // Length of the ATR for volatility measurement
vegasWindow1 = input(100, "Vegas Window Length 1") // Length of the moving average for the Vegas Channel
superTrendMultiplier1 = input(5, "SuperTrend Multiplier Base 1") // Base multiplier for the SuperTrend calculation
volatilityAdjustment1 = input.float(5, "Volatility Adjustment Factor 1") // Factor to adjust the SuperTrend sensitivity to the Vegas Channel width

// Settings for the second Vegas SuperTrend
atrPeriod2 = input(5, "ATR Period for SuperTrend 2") // Length of the ATR for volatility measurement
vegasWindow2 = input(200, "Vegas Window Length 2") // Length of the moving average for the Vegas Channel
superTrendMultiplier2 = input(7, "SuperTrend Multiplier Base 2") // Base multiplier for the SuperTrend calculation
volatilityAdjustment2 = input.float(7, "Volatility Adjustment Factor 2") // Factor to adjust the SuperTrend sensitivity to the Vegas Channel width

// Settings for Hold Days and TPSL Conditions
useHoldDays = input.bool(true, title="Use Hold Days")
holdDays = input.int(5, title="Hold Days", minval=1, maxval=60, step=1)
TPSLCondition = input.string("None", "TPSL Condition", options=["TP", "SL", "Both", "None"])
takeProfitPerc = input(30.0, title="Take Profit (%)")
stopLossPerc = input(20.0, title="Stop Loss (%)")

// Calculate the first Vegas Channel using a simple moving average and standard deviation.
vegasMovingAverage1 = ta.sma(close, vegasWindow1)
vegasChannelStdDev1 = ta.stdev(close, vegasWindow1)
vegasChannelUpper1 = vegasMovingAverage1 + vegasChannelStdDev1
vegasChannelLower1 = vegasMovingAverage1 - vegasChannelStdDev1

// Adjust the first SuperTrend multiplier based on the width of the Vegas Channel.
channelVolatilityWidth1 = vegasChannelUpper1 - vegasChannelLower1
adjustedMultiplier1 = superTrendMultiplier1 + volatilityAdjustment1 * (channelVolatilityWidth1 / vegasMovingAverage1)

// Calculate the first SuperTrend indicator values.
averageTrueRange1 = ta.atr(atrPeriod1)
superTrendUpper1 = hlc3 - (adjustedMultiplier1 * averageTrueRange1)
superTrendLower1 = hlc3 + (adjustedMultiplier1 * averageTrueRange1)
var float superTrendPrevUpper1 = na
var float superTrendPrevLower1 = na
var int marketTrend1 = 1

// Update SuperTrend values and determine the current trend direction for the first SuperTrend.
superTrendPrevUpper1 := nz(superTrendPrevUpper1[1], superTrendUpper1)
superTrendPrevLower1 := nz(superTrendPrevLower1[1], superTrendLower1)
marketTrend1 := close > superTrendPrevLower1 ? 1 : close < superTrendPrevUpper1 ? -1 : nz(marketTrend1[1], 1)
superTrendUpper1 := marketTrend1 == 1 ? math.max(superTrendUpper1, superTrendPrevUpper1) : superTrendUpper1
superTrendLower1 := marketTrend1 == -1 ? math.min(superTrendLower1, superTrendPrevLower1) : superTrendLower1
superTrendPrevUpper1 := superTrendUpper1
superTrendPrevLower1 := superTrendLower1

// Calculate the second Vegas Channel using a simple moving average and standard deviation.
vegasMovingAverage2 = ta.sma(close, vegasWindow2)
vegasChannelStdDev2 = ta.stdev(close, vegasWindow2)
vegasChannelUpper2 = vegasMovingAverage2 + vegasChannelStdDev2
vegasChannelLower2 = vegasMovingAverage2 - vegasChannelStdDev2

// Adjust the second SuperTrend multiplier based on the width of the Vegas Channel.
channelVolatilityWidth2 = vegasChannelUpper2 - vegasChannelLower2
adjustedMultiplier2 = superTrendMultiplier2 + volatilityAdjustment2 * (channelVolatilityWidth2 / vegasMovingAverage2)

// Calculate the second SuperTrend indicator values.
averageTrueRange2 = ta.atr(atrPeriod2)
superTrendUpper2 = hlc3 - (adjustedMultiplier2 * averageTrueRange2)
superTrendLower2 = hlc3 + (adjustedMultiplier2 * averageTrueRange2)
var float superTrendPrevUpper2 = na
var float superTrendPrevLower2 = na
var int marketTrend2 = 1

// Update SuperTrend values and determine the current trend direction for the second SuperTrend.
superTrendPrevUpper2 := nz(superTrendPrevUpper2[1], superTrendUpper2)
superTrendPrevLower2 := nz(superTrendPrevLower2[1], superTrendLower2)
marketTrend2 := close > superTrendPrevLower2 ? 1 : close < superTrendPrevUpper2 ? -1 : nz(marketTrend2[1], 1)
superTrendUpper2 := marketTrend2 == 1 ? math.max(superTrendUpper2, superTrendPrevUpper2) : superTrendUpper2
superTrendLower2 := marketTrend2 == -1 ? math.min(superTrendLower2, superTrendPrevLower2) : superTrendLower2
superTrendPrevUpper2 := superTrendUpper2
superTrendPrevLower2 := superTrendLower2

// Enhanced Visualization
// Plot the SuperTrend and Vegas Channel for visual analysis for both lengths.
plot(marketTrend1 == 1 ? superTrendUpper1 : na, "SuperTrend Upper 1", color=color.green, linewidth=2)
plot(marketTrend1 == -1 ? superTrendLower1 : na, "SuperTrend Lower 1", color=color.red, linewidth=2)

plot(marketTrend2 == 1 ? superTrendUpper2 : na, "SuperTrend Upper 2", color=color.rgb(31, 119, 130), linewidth=2)
plot(marketTrend2 == -1 ? superTrendLower2 : na, "SuperTrend Lower 2", color=color.rgb(120, 42, 26), linewidth=2)

// Detect trend direction changes and plot entry/exit signals for both lengths.
trendShiftToBullish1 = marketTrend1 == 1 and marketTrend1[1] == -1
trendShiftToBearish1 = marketTrend1 == -1 and marketTrend1[1] == 1

trendShiftToBullish2 = marketTrend2 == 1 and marketTrend2[1] == -1
trendShiftToBearish2 = marketTrend2 == -1 and marketTrend2[1] == 1

// Define conditions for entering long or short positions, and execute trades based on these conditions for both lengths.
enterLongCondition1 = marketTrend1 == 1
enterShortCondition1 = marketTrend1 == -1

enterLongCondition2 = marketTrend2 == 1
enterShortCondition2 = marketTrend2 == -1

// Entry conditions: Both conditions must be met for a trade to be executed.
enterLongCondition = enterLongCondition1 and enterLongCondition2 and not na(superTrendPrevUpper1[1]) and not na(superTrendPrevUpper2[1])
enterShortCondition = enterShortCondition1 and enterShortCondition2 and not na(superTrendPrevLower1[1]) and not na(superTrendPrevLower2[1])

// Variables to track entry times
var float longEntryTime = na
var float shortEntryTime = na

// Variables to track whether we have recently exited a trade to prevent re-entry in the same trend
var bool recentlyExitedLong = false
var bool recentlyExitedShort = false

// Check trade direction choice before executing trade entries.
if (enterLongCondition and (tradeDirectionChoice == "Long" or tradeDirectionChoice == "Both"))
    if (strategy.position_size < 0)
        strategy.close("Short Position")
    strategy.entry("Long Position", strategy.long)
    longEntryTime := time
    recentlyExitedLong := false
    recentlyExitedShort := false

if (enterShortCondition and (tradeDirectionChoice == "Short" or tradeDirectionChoice == "Both"))
    if (strategy.position_size > 0)
        strategy.close("Long Position")
    strategy.entry("Short Position", strategy.short)
    shortEntryTime := time
    recentlyExitedShort := false
    recentlyExitedLong := false

// Exit conditions: Either condition being met will trigger an exit.
exitLongCondition = marketTrend1 == -1 or marketTrend2 == -1
exitShortCondition = marketTrend1 == 1 or marketTrend2 == 1

// Close positions based on exit conditions or hold days.
if (useHoldDays and not na(longEntryTime) and (time >= longEntryTime + holdDays * 86400000) and strategy.position_size > 0)
    strategy.close("Long Position")
    longEntryTime := na
    recentlyExitedLong := true

if (useHoldDays and not na(shortEntryTime) and (time >= shortEntryTime + holdDays * 86400000) and strategy.position_size < 0)
    strategy.close("Short Position")
    shortEntryTime := na
    recentlyExitedShort := true

if (not useHoldDays and exitLongCondition and strategy.position_size > 0)
    strategy.close("Long Position")
    longEntryTime := na
    recentlyExitedLong := true

if (not useHoldDays and exitShortCondition and strategy.position_size < 0)
    strategy.close("Short Position")
    shortEntryTime := na
    recentlyExitedShort := true

// Reset recently exited flags on trend change to allow re-entry on a new trend
if (trendShiftToBullish1 or trendShiftToBullish2)
    recentlyExitedLong := false

if (trendShiftToBearish1 or trendShiftToBearish2)
    recentlyExitedShort := false

// Conditional Profit and Loss Management
if (TPSLCondition == "TP" or TPSLCondition == "Both") 
    // Apply take profit conditions
    strategy.exit("TakeProfit_Long", "Long Position", limit=close * (1 + takeProfitPerc / 100))
    strategy.exit("TakeProfit_Short", "Short Position", limit=close * (1 - takeProfitPerc / 100))

if (TPSLCondition == "SL" or TPSLCondition == "Both") 
    // Apply stop loss conditions
    strategy.exit("StopLoss_Long", "Long Position", stop=close * (1 - stopLossPerc / 100))
    strategy.exit("StopLoss_Short", "Short Position", stop=close * (1 + stopLossPerc / 100))

// Ensure that new entry signals can override the hold days condition
if (enterLongCondition and (tradeDirectionChoice == "Long" or tradeDirectionChoice == "Both"))
    if (strategy.position_size < 0)
        strategy.close("Short Position")
    strategy.entry("Long Position", strategy.long)
    longEntryTime := time
    recentlyExitedLong := false
    recentlyExitedShort := false

if (enterShortCondition and (tradeDirectionChoice == "Short" or tradeDirectionChoice == "Both"))
    if (strategy.position_size > 0)
        strategy.close("Long Position")
    strategy.entry("Short Position", strategy.short)
    shortEntryTime := time
    recentlyExitedShort := false
    recentlyExitedLong := false

```

> Detail

https://www.fmz.com/strategy/453242

> Last Modified

2024-06-03 11:16:38
