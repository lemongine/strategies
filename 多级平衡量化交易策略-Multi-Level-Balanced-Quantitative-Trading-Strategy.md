
> Name

多级平衡量化交易策略-Multi-Level-Balanced-Quantitative-Trading-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/1053a0b36aad27282a3.png)

[trans]
#### 概述
多级平衡量化交易策略是一种结合多个技术指标和价格水平的复杂交易系统。该策略利用MACD、RSI、EMA和布林带等指标,结合斐波那契回撤水平,在不同价格区间采取不同的交易策略,以实现多层次的平衡交易。策略的核心思想是通过多重确认来增加交易的准确性,同时通过逐步加仓来优化资金管理。

#### 策略原理
该策略的核心原理包括以下几个方面:
1. 使用MACD、RSI和EMA指标来确定市场趋势和动量。
2. 利用布林带和斐波那契回撤水平来识别关键支撑和阻力位。
3. 在不同的价格水平设置多个交易入场点,实现逐步建仓。
4. 通过设置不同的止盈和止损水平来管理风险。
5. 使用海肯阿希蜡烛图来提供额外的市场结构信息。

策略通过综合分析这些因素,在不同的市场条件下采取相应的交易行为,以实现稳定的收益。

#### 策略优势
1. 多重确认: 通过结合多个技术指标,提高了交易信号的可靠性。
2. 灵活的资金管理: 采用逐步加仓的方式,可以更好地控制风险并优化资金利用。
3. 适应性强: 策略可以根据不同的市场条件调整交易行为。
4. 全面的风险管理: 设置了多层次的止损和止盈机制,有效控制风险。
5. 自动化程度高: 策略可以完全自动化执行,减少人为干预。

#### 策略风险
1. 过度交易: 由于策略设置了多个交易级别,可能导致频繁交易,增加交易成本。
2. 参数敏感性: 策略使用了多个指标和参数,需要仔细调整以适应不同的市场环境。
3. 回撤风险: 在剧烈波动的市场中,可能面临较大的回撤风险。
4. 技术依赖: 策略高度依赖技术指标,可能在某些市场条件下失效。
5. 资金管理风险: 逐步加仓的方式可能在某些情况下导致过度暴露。

#### 策略优化方向
1. 动态参数调整: 引入机器学习算法,根据市场状况自动调整策略参数。
2. 市场情绪分析: 整合市场情绪指标,如VIX指数,提高策略的适应性。
3. 多时间框架分析: 引入多时间框架分析,以提高交易信号的可靠性。
4. 波动率调整: 根据市场波动率动态调整交易量和止损水平。
5. 交易成本优化: 引入交易成本模型,优化交易频率和规模。

#### 总结
多级平衡量化交易策略是一种综合性强、适应性好的交易系统。通过结合多个技术指标和价格水平,该策略能够在不同市场环境下保持稳定性。虽然存在一些风险,但通过持续优化和调整,这些风险可以得到有效控制。未来,通过引入更先进的技术如机器学习和情绪分析,该策略有望实现更好的表现。对于寻求全面、自动化交易解决方案的投资者来说,这是一个值得考虑的选择。

|| 

#### Overview
The Multi-Level Balanced Quantitative Trading Strategy is a complex trading system that combines multiple technical indicators and price levels. This strategy utilizes indicators such as MACD, RSI, EMA, and Bollinger Bands, along with Fibonacci retracement levels, to implement different trading tactics at various price ranges, achieving multi-level balanced trading. The core idea of the strategy is to increase trading accuracy through multiple confirmations while optimizing capital management through gradual position building.

#### Strategy Principles
The core principles of this strategy include:
1. Using MACD, RSI, and EMA indicators to determine market trends and momentum.
2. Utilizing Bollinger Bands and Fibonacci retracement levels to identify key support and resistance levels.
3. Setting multiple entry points at different price levels to achieve gradual position building.
4. Managing risk through different take-profit and stop-loss levels.
5. Using Heikin Ashi candlesticks to provide additional market structure information.

The strategy comprehensively analyzes these factors to take appropriate trading actions under different market conditions, aiming to achieve stable returns.

#### Strategy Advantages
1. Multiple Confirmations: Combining multiple technical indicators increases the reliability of trading signals.
2. Flexible Capital Management: The gradual position building approach allows for better risk control and capital utilization optimization.
3. High Adaptability: The strategy can adjust trading behavior according to different market conditions.
4. Comprehensive Risk Management: Multiple levels of stop-loss and take-profit mechanisms effectively control risk.
5. High Degree of Automation: The strategy can be fully automated, reducing human intervention.

#### Strategy Risks
1. Over-trading: The multiple trading levels may lead to frequent trading, increasing transaction costs.
2. Parameter Sensitivity: The strategy uses multiple indicators and parameters, requiring careful adjustment to adapt to different market environments.
3. Drawdown Risk: In highly volatile markets, the strategy may face significant drawdown risks.
4. Technical Dependence: The strategy heavily relies on technical indicators, which may fail under certain market conditions.
5. Capital Management Risk: The gradual position building approach may lead to overexposure in certain situations.

#### Strategy Optimization Directions
1. Dynamic Parameter Adjustment: Introduce machine learning algorithms to automatically adjust strategy parameters based on market conditions.
2. Market Sentiment Analysis: Integrate market sentiment indicators, such as the VIX index, to improve strategy adaptability.
3. Multi-Timeframe Analysis: Introduce multi-timeframe analysis to enhance the reliability of trading signals.
4. Volatility Adjustment: Dynamically adjust trading volume and stop-loss levels based on market volatility.
5. Transaction Cost Optimization: Introduce a transaction cost model to optimize trading frequency and size.

#### Summary
The Multi-Level Balanced Quantitative Trading Strategy is a comprehensive and adaptive trading system. By combining multiple technical indicators and price levels, this strategy can maintain stability in different market environments. Although there are some risks, they can be effectively controlled through continuous optimization and adjustment. In the future, by introducing more advanced technologies such as machine learning and sentiment analysis, this strategy has the potential to achieve better performance. For investors seeking a comprehensive, automated trading solution, this is a worthy option to consider.

[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2019-12-23 08:00:00
end: 2024-10-12 08:00:00
period: 1d
basePeriod: 1d
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

//@version=5
strategy(title='Incremental Order size +', shorttitle='TradingPost', overlay=true, default_qty_value=1, pyramiding=10)

//Heiken Ashi
isHA = input(false, 'HA Candles')

//MACD
fastLength = 12
slowlength = 26
MACDLength = 9

MACD = ta.ema(close, fastLength) - ta.ema(close, slowlength)
aMACD = ta.ema(MACD, MACDLength)
delta = MACD - aMACD

//Bollinger Bands Exponential
src = open
len = 18
e = ta.ema(src, len)
evar = (src - e) * (src - e)
evar2 = math.sum(evar, len) / len
std = math.sqrt(evar2)
Multiplier = input.float(3, minval=0.01, title='# of STDEV\'s')
upband = e + Multiplier * std
dnband = e - Multiplier * std

//EMA
ema3 = ta.ema(close, 3)

//RSIplot
length = 45
overSold = 90
overBought = 10
price = close

vrsi = ta.rsi(price, length)

notna = not na(vrsi)

macdlong = ta.crossover(delta, 0)
macdshort = ta.crossunder(delta, 0)
rsilong = notna and ta.crossover(vrsi, overSold)
rsishort = notna and ta.crossunder(vrsi, overBought)

lentt = input(14, 'Pivot Length')
    //The length defines how many periods a high or low must hold to be a "relevant pivot"

h = ta.highest(lentt)
    //The highest high over the length
h1 = ta.dev(h, lentt) ? na : h
    //h1 is a pivot of h if it holds for the full length
hpivot = fixnan(h1)
    //creates a series which is equal to the last pivot

l = ta.lowest(lentt)
l1 = ta.dev(l, lentt) ? na : l
lpivot = fixnan(l1)
    //repeated for lows

last_hpivot = 0.0
last_lpivot = 0.0
last_hpivot := h1 ? time : nz(last_hpivot[1])
last_lpivot := l1 ? time : nz(last_lpivot[1])

long_time = last_hpivot > last_lpivot ? 0 : 1

//FIBS

z = input(100, 'Z-Index')
p_offset = 2
transp = 60
a = (ta.lowest(z) + ta.highest(z)) / 2
b = ta.lowest(z)
c = ta.highest(z)
fibonacci = input(0, 'Fibonacci') / 100

//Fib Calls
fib0 = (hpivot - lpivot) * fibonacci + lpivot
fib1 = (hpivot - lpivot) * .21 + lpivot
fib2 = (hpivot - lpivot) * .3 + lpivot
fib3 = (hpivot - lpivot) * .5 + lpivot
fib4 = (hpivot - lpivot) * .62 + lpivot
fib5 = (hpivot - lpivot) * .7 + lpivot
fib6 = (hpivot - lpivot) * 1.00 + lpivot
fib7 = (hpivot - lpivot) * 1.27 + lpivot
fib8 = (hpivot - lpivot) * 2 + lpivot
fib9 = (hpivot - lpivot) * -.27 + lpivot
fib10 = (hpivot - lpivot) * -1 + lpivot

//Heiken Ashi Candles

heikenashi_1 = ticker.heikinashi(syminfo.tickerid)
data2 = isHA ? heikenashi_1 : syminfo.tickerid
res5 = input.timeframe('5', 'Resolution')

//HT Fibs

hfib0 = request.security(data2, res5, fib0[1])
hfib1 = request.security(data2, res5, fib1[1])
hfib2 = request.security(data2, res5, fib2[1])
hfib3 = request.security(data2, res5, fib3[1])
hfib4 = request.security(data2, res5, fib4[1])
hfib5 = request.security(data2, res5, fib5[1])
hfib6 = request.security(data2, res5, fib6[1])
hfib7 = request.security(data2, res5, fib7[1])
hfib8 = request.security(data2, res5, fib8[1])
hfib9 = request.security(data2, res5, fib9[1])
hfib10 = request.security(data2, res5, fib10[1])

vrsiup = vrsi > vrsi[1] and vrsi[1] > vrsi[2]
vrsidown = vrsi < vrsi[1] and vrsi[1] < vrsi[2]

long = ta.cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup
short = ta.cross(close, fib6) and delta < 0 and vrsi > overBought and vrsidown

 // long2 =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
 // short2 = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown
// long =  cross(close, fib0) and delta > 0 and vrsi < overSold and vrsiup 
// short = cross(close, fib6) and delta < 0  and vrsi > overBought and vrsidown

reverseOpens = input(false, 'Reverse Orders')
if reverseOpens
    tmplong = long
    long := short
    short := tmplong
    short

//Strategy
ts = input(99999, 'TS')
tp = input(30, 'TP')
sl = input(15, 'SL')

last_long = 0.0
last_short = 0.0
last_long := long ? time : nz(last_long)
last_short := short ? time : nz(last_short)

in_long = last_long > last_short
in_short = last_short > last_long

long_signal = ta.crossover(last_long, last_short)
short_signal = ta.crossover(last_short, last_long)

last_open_long = 0.0
last_open_short = 0.0
last_open_long := long ? open : nz(last_open_long[1])
last_open_short := short ? open : nz(last_open_short[1])

last_open_long_signal = 0.0
last_open_short_signal = 0.0
last_open_long_signal := long_signal ? open : nz(last_open_long_signal[1])
last_open_short_signal := short_signal ? open : nz(last_open_short_signal[1])

last_high = 0.0
last_low = 0.0
last_high := not in_long ? na : in_long and (na(last_high[1]) or high > nz(last_high[1])) ? high : nz(last_high[1])
last_low := not in_short ? na : in_short and (na(last_low[1]) or low < nz(last_low[1])) ? low : nz(last_low[1])

long_ts = not na(last_high) and high <= last_high - ts and high >= last_open_long_signal
short_ts = not na(last_low) and low >= last_low + ts and low <= last_open_short_signal

long_tp = high >= last_open_long + tp and long[1] == 0
short_tp = low <= last_open_short - tp and short[1] == 0

long_sl = low <= last_open_long - sl and long[1] == 0
short_sl = high >= last_open_short + sl and short[1] == 0

last_hfib_long = 0.0
last_hfib_short = 0.0
last_hfib_long := long_signal ? fib1 : nz(last_hfib_long[1])
last_hfib_short := short_signal ? fib5 : nz(last_hfib_short[1])

last_fib7 = 0.0
last_fib10 = 0.0
last_fib7 := long ? fib7 : nz(last_fib7[1])
last_fib10 := long ? fib10 : nz(last_fib10[1])

last_fib8 = 0.0
last_fib9 = 0.0
last_fib8 := short ? fib8 : nz(last_fib8[1])
last_fib9 := short ? fib9 : nz(last_fib9[1])

last_long_signal = 0.0
last_short_signal = 0.0
last_long_signal := long_signal ? time : nz(last_long_signal[1])
last_short_signal := short_signal ? time : nz(last_short_signal[1])

last_long_tp = 0.0
last_short_tp = 0.0
last_long_tp := long_tp ? time : nz(last_long_tp[1])
last_short_tp := short_tp ? time : nz(last_short_tp[1])

last_long_ts = 0.0
last_short_ts = 0.0
last_long_ts := long_ts ? time : nz(last_long_ts[1])
last_short_ts := short_ts ? time : nz(last_short_ts[1])

long_ts_signal = ta.crossover(last_long_ts, last_long_signal)
short_ts_signal = ta.crossover(last_short_ts, last_short_signal)

last_long_sl = 0.0
last_short_sl = 0.0
last_long_sl := long_sl ? time : nz(last_long_sl[1])
last_short_sl := short_sl ? time : nz(last_short_sl[1])

long_tp_signal = ta.crossover(last_long_tp, last_long)
short_tp_signal = ta.crossover(last_short_tp, last_short)

long_sl_signal = ta.crossover(last_long_sl, last_long)
short_sl_signal = ta.crossover(last_short_sl, last_short)

last_long_tp_signal = 0.0
last_short_tp_signal = 0.0
last_long_tp_signal := long_tp_signal ? time : nz(last_long_tp_signal[1])
last_short_tp_signal := short_tp_signal ? time : nz(last_short_tp_signal[1])

last_long_sl_signal = 0.0
last_short_sl_signal = 0.0
last_long_sl_signal := long_sl_signal ? time : nz(last_long_sl_signal[1])
last_short_sl_signal := short_sl_signal ? time : nz(last_short_sl_signal[1])

last_long_ts_signal = 0.0
last_short_ts_signal = 0.0
last_long_ts_signal := long_ts_signal ? time : nz(last_long_ts_signal[1])
last_short_ts_signal := short_ts_signal ? time : nz(last_short_ts_signal[1])

true_long_signal = long_signal and last_long_sl_signal > last_long_signal[1] or long_signal and last_long_tp_signal > last_long_signal[1] or long_signal and last_long_ts_signal > last_long_signal[1]
true_short_signal = short_signal and last_short_sl_signal > last_short_signal[1] or short_signal and last_short_tp_signal > last_short_signal[1] or short_signal and last_short_ts_signal > last_short_signal[1]


// strategy.entry("BLUE", strategy.long, when=long)
// strategy.entry("RED", strategy.short, when=short)

g = delta > 0 and vrsi < overSold and vrsiup
r = delta < 0 and vrsi > overBought and vrsidown

long1 = ta.cross(close, fib1) and g and last_long_signal[1] > last_short_signal  // and last_long_signal > long
short1 = ta.cross(close, fib5) and r and last_short_signal[1] > last_long_signal  // and last_short_signal > short

last_long1 = 0.0
last_short1 = 0.0
last_long1 := long1 ? time : nz(last_long1[1])
last_short1 := short1 ? time : nz(last_short1[1])

last_open_long1 = 0.0
last_open_short1 = 0.0
last_open_long1 := long1 ? open : nz(last_open_long1[1])
last_open_short1 := short1 ? open : nz(last_open_short1[1])

long1_signal = ta.crossover(last_long1, last_long_signal)
short1_signal = ta.crossover(last_short1, last_short_signal)

last_long1_signal = 0.0
last_short1_signal = 0.0
last_long1_signal := long1_signal ? time : nz(last_long1_signal[1])
last_short1_signal := short1_signal ? time : nz(last_short1_signal[1])

long2 = ta.cross(close, fib2) and g and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short2 = ta.cross(close, fib4) and r and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal

last_long2 = 0.0
last_short2 = 0.0
last_long2 := long2 ? time : nz(last_long2[1])
last_short2 := short2 ? time : nz(last_short2[1])

last_open_short2 = 0.0
last_open_short2 := short2 ? open : nz(last_open_short2[1])

long2_signal = ta.crossover(last_long2, last_long1_signal) and long1_signal == 0
short2_signal = ta.crossover(last_short2, last_short1_signal) and short1_signal == 0

last_long2_signal = 0.0
last_short2_signal = 0.0
last_long2_signal := long2_signal ? time : nz(last_long2_signal[1])
last_short2_signal := short2_signal ? time : nz(last_short2_signal[1])

//Trade 4

long3 = ta.cross(close, fib3) and g and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short3 = ta.cross(close, fib3) and r and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal

last_long3 = 0.0
last_short3 = 0.0
last_long3 := long3 ? time : nz(last_long3[1])
last_short3 := short3 ? time : nz(last_short3[1])

last_open_short3 = 0.0
last_open_short3 := short3 ? open : nz(last_open_short3[1])

long3_signal = ta.crossover(last_long3, last_long2_signal) and long2_signal == 0
short3_signal = ta.crossover(last_short3, last_short2_signal) and short2_signal == 0

last_long3_signal = 0.0
last_short3_signal = 0.0
last_long3_signal := long3_signal ? time : nz(last_long3_signal[1])
last_short3_signal := short3_signal ? time : nz(last_short3_signal[1])


//Trade 5
long4 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short4 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal
last_long4 = 0.0
last_short4 = 0.0
last_long4 := long4 ? time : nz(last_long4[1])
last_short4 := short4 ? time : nz(last_short4[1])

long4_signal = ta.crossover(last_long4, last_long3_signal) and long2_signal == 0 and long3_signal == 0
short4_signal = ta.crossover(last_short4, last_short3_signal) and short2_signal == 0 and short3_signal == 0
last_long4_signal = 0.0
last_short4_signal = 0.0
last_long4_signal := long4_signal ? time : nz(last_long4_signal[1])
last_short4_signal := short4_signal ? time : nz(last_short4_signal[1])

//Trade 6
long5 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short5 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal

last_long5 = 0.0
last_short5 = 0.0
last_long5 := long5 ? time : nz(last_long5[1])
last_short5 := short5 ? time : nz(last_short5[1])

long5_signal = ta.crossover(last_long5, last_long4_signal) and long3_signal == 0 and long4_signal == 0
short5_signal = ta.crossover(last_short5, last_short4_signal) and short3_signal == 0 and short4_signal == 0

last_long5_signal = 0.0
last_short5_signal = 0.0
last_long5_signal := long5_signal ? time : nz(last_long5_signal[1])
last_short5_signal := short5_signal ? time : nz(last_short5_signal[1])

//Trade 7
long6 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short6 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal

last_long6 = 0.0
last_short6 = 0.0
last_long6 := long6 ? time : nz(last_long6[1])
last_short6 := short6 ? time : nz(last_short6[1])

long6_signal = ta.crossover(last_long6, last_long5_signal) and long2_signal == 0 and long4_signal == 0 and long5_signal == 0
short6_signal = ta.crossover(last_short6, last_short5_signal) and short2_signal == 0 and short4_signal == 0 and short5_signal == 0

last_long6_signal = 0.0
last_short6_signal = 0.0
last_long6_signal := long6_signal ? time : nz(last_long6_signal[1])
last_short6_signal := short6_signal ? time : nz(last_short6_signal[1])


//Trade 8
long7 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short7 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal

last_long7 = 0.0
last_short7 = 0.0
last_long7 := long7 ? time : nz(last_long7[1])
last_short7 := short7 ? time : nz(last_short7[1])

long7_signal = ta.crossover(last_long7, last_long6_signal) and long2_signal == 0 and long4_signal == 0 and long5_signal == 0 and long6_signal == 0
short7_signal = ta.crossover(last_short7, last_short6_signal) and short2_signal == 0 and short4_signal == 0 and short5_signal == 0 and short6_signal == 0

last_long7_signal = 0.0
last_short7_signal = 0.0
last_long7_signal := long7_signal ? time : nz(last_long7_signal[1])
last_short7_signal := short7_signal ? time : nz(last_short7_signal[1])


//Trade 9
long8 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short8 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal
last_long8 = 0.0
last_short8 = 0.0
last_long8 := long8 ? time : nz(last_long8[1])
last_short8 := short8 ? time : nz(last_short8[1])

long8_signal = ta.crossover(last_long8, last_long7_signal) and long2_signal == 0 and long4_signal == 0 and long5_signal == 0 and long6_signal == 0 and long7_signal == 0
short8_signal = ta.crossover(last_short8, last_short7_signal) and short2_signal == 0 and short4_signal == 0 and short5_signal == 0 and short6_signal == 0 and short7_signal == 0

last_long8_signal = 0.0
last_short8_signal = 0.0
last_long8_signal := long8_signal ? time : nz(last_long8_signal[1])
last_short8_signal := short8_signal ? time : nz(last_short8_signal[1])

//Trade 10
long9 = long and last_long1_signal > last_long_signal[1] and long1_signal == 0 and last_long_signal[1] > last_short_signal
short9 = short and last_short1_signal > last_short_signal[1] and short1_signal == 0 and last_short_signal[1] > last_long_signal
last_long9 = 0.0
last_short9 = 0.0
last_long9 := long9 ? time : nz(last_long9[1])
last_short9 := short9 ? time : nz(last_short9[1])

long9_signal = ta.crossover(last_long9, last_long8_signal) and long2_signal == 0 and long4_signal == 0 and long5_signal == 0 and long6_signal == 0 and long7_signal == 0 and long8_signal == 0
short9_signal = ta.crossover(last_short9, last_short8_signal) and short2_signal == 0 and short4_signal == 0 and short5_signal == 0 and short6_signal == 0 and short7_signal == 0 and short8_signal == 0
last_long9_signal = 0.0
last_short9_signal = 0.0
last_long9_signal := long9_signal ? time : nz(last_long9_signal[1])
last_short9_signal := short9_signal ? time : nz(last_short9_signal[1])


strategy.entry('Long', strategy.long, qty=1, when=long_signal)
strategy.entry('Short', strategy.short, qty=1, when=short_signal)
strategy.entry('Long', strategy.long, qty=2, when=long1_signal)
strategy.entry('Short1', strategy.short, qty=2, when=short1_signal)
strategy.entry('Long', strategy.long, qty=4, when=long2_signal)
strategy.entry('Short2', strategy.short, qty=4, when=short2_signal)
strategy.entry('Long', strategy.long, qty=8, when=long3_signal)
strategy.entry('Short3', strategy.short, qty=8, when=short3_signal)
strategy.entry('Long', strategy.long, qty=5, when=long4_signal)
strategy.entry('Short', strategy.short, qty=5, when=short4_signal)
strategy.entry('Long', strategy.long, qty=6, when=long5_signal)
strategy.entry('Short', strategy.short, qty=6, when=short5_signal)
strategy.entry('Long', strategy.long, qty=7, when=long6_signal)
strategy.entry('Short', strategy.short, qty=7, when=short6_signal)
strategy.entry('Long', strategy.long, qty=8, when=long7_signal)
strategy.entry('Short', strategy.short, qty=8, when=short7_signal)
strategy.entry('Long', strategy.long, qty=9, when=long8_signal)
strategy.entry('Short', strategy.short, qty=9, when=short8_signal)
strategy.entry('Long', strategy.long, qty=10, when=long9_signal)
strategy.entry('Short', strategy.short, qty=10, when=short9_signal)

short1_tp = low <= last_open_short1 - tp and short1[1] == 0
short2_tp = low <= last_open_short2 - tp and short2[1] == 0
short3_tp = low <= last_open_short3 - tp and short3[1] == 0
short1_sl = high >= last_open_short1 + sl and short1[1] == 0
short2_sl = high >= last_open_short2 + sl and short2[1] == 0
short3_sl = high >= last_open_short3 + sl and short3[1] == 0

close_long = ta.cross(close, fib6)
close_short = ta.cross(close, fib0)

// strategy.close("Long", when=close_long)
// strategy.close("Long", when=long_tp)
// strategy.close("Long", when=long_sl)

// strategy.close("Short", when=long_signal)
// strategy.close("Short1", when=long_signal)
// strategy.close("Short2", when=long_signal)
// strategy.close("Short3", when=long_signal)
strategy.close('Short', when=short_tp)
strategy.close('Short1', when=short1_tp)
strategy.close('Short2', when=short2_tp)
strategy.close('Short3', when=short3_tp)
strategy.close('Short', when=short_sl)
strategy.close('Short1', when=short1_sl)
strategy.close('Short2', when=short2_sl)
strategy.close('Short3', when=short3_sl)


```

> Detail

https://www.fmz.com/strategy/469612

> Last Modified

2024-10-14 11:23:45
