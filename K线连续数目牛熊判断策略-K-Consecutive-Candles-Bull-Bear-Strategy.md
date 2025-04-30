
> Name

K线连续数目牛熊判断策略-K-Consecutive-Candles-Bull-Bear-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/1e0f433500bd65b3cc4.png)

[trans]
#### 概述
该策略基于K线的连续上涨或下跌数目来判断牛市或熊市,并据此进行交易。当收盘价连续高于前一根K线的收盘价达到指定数目时,开多头仓位;当收盘价连续低于前一根K线的收盘价达到指定数目时,开空头仓位。同时设置了止损和止盈,并引入了移动止盈的机制以保护利润。

#### 策略原理
1. 记录连续多头和空头条件成立的次数。如果收盘价高于前一根K线,多头计数加1,空头计数重置为0;如果收盘价低于前一根K线,空头计数加1,多头计数重置为0;否则两个计数都重置为0。
2. 当多头计数达到指定数目k时,开多头仓位,设置止损和止盈。
3. 对于多头仓位,记录开仓后最高价,当最高价超过开仓价iTGT个最小变动单位,且收盘价回撤至最高价下方iPcnt%时,平仓。
4. 当空头计数达到指定数目k2时,开空头仓位,设置止损和止盈。 
5. 对于空头仓位,记录开仓后最低价,当最低价低于开仓价iTGT个最小变动单位,且收盘价反弹至最低价上方iPcnt%时,平仓。

#### 策略优势
1. 简单易懂,基于K线的连续性进行交易决策,逻辑清晰。
2. 引入了移动止盈的机制,在价格朝有利方向运行一段距离后主动保护利润。
3. 止损和止盈的设置可以有效控制风险和锁定利润。
4. 参数可调,适用于不同的市场和交易风格。

#### 策略风险
1. 在震荡行情中,频繁的开平仓可能导致较大的滑点成本。
2. 连续K线数目的判断受到市场噪音的影响,可能出现频繁的信号。
3. 固定的止损和止盈点位可能无法适应市场的波动性变化。

#### 策略优化方向
1. 引入更多的技术指标,如均线、波动率等,辅助判断趋势的强度和方向。
2. 优化移动止盈的触发条件,如根据ATR自适应调整回撤百分比。
3. 采用更加动态的止损和止盈方式,如跟踪止损、阶梯式止盈等。
4. 对参数进行优化,找到适合不同市场和品种的最优参数组合。

#### 总结
该策略通过K线的连续性来捕捉牛熊趋势,同时设置了止损止盈以控制风险。移动止盈的引入可以更好地保护利润。但在震荡市中可能出现频繁信号,需要进一步优化信号的可靠性。此外,止损止盈的设置也可以更加灵活,以适应市场的动态变化。综合来看,该策略思路简单清晰,适合趋势性市场,但仍有优化的空间。

|| 

#### Overview
This strategy determines bull or bear markets based on the number of consecutive up or down candles and makes trades accordingly. When the closing price is consecutively higher than the previous candle's close for a specified number of times, it enters a long position; when the closing price is consecutively lower than the previous candle's close for a specified number of times, it enters a short position. Stop loss and take profit are set, and a trailing stop mechanism is introduced to protect profits.

#### Strategy Principle
1. Record the number of times the consecutive bullish and bearish conditions are met. If the close is higher than the previous candle, the bullish count increases by 1 and the bearish count resets to 0; if the close is lower, the bearish count increases by 1 and the bullish count resets to 0; otherwise, both counts reset to 0.
2. When the bullish count reaches the specified number k, enter a long position with stop loss and take profit.
3. For long positions, record the highest price after entry. When the highest price exceeds the entry price by iTGT minimum price variation units and the close pulls back below the highest price by iPcnt%, close the position.
4. When the bearish count reaches the specified number k2, enter a short position with stop loss and take profit.
5. For short positions, record the lowest price after entry. When the lowest price is lower than the entry price by iTGT minimum price variation units and the close rebounds above the lowest price by iPcnt%, close the position.

#### Strategy Advantages
1. Simple and easy to understand, making trading decisions based on the continuity of candles with clear logic.
2. Introduces a trailing stop mechanism to actively protect profits after the price moves a certain distance in the favorable direction.
3. Setting stop loss and take profit can effectively control risks and lock in profits.
4. Adjustable parameters to suit different markets and trading styles.

#### Strategy Risks
1. In choppy markets, frequent opening and closing of positions may lead to large slippage costs.
2. The judgment of consecutive candle numbers is affected by market noise, which may result in frequent signals.
3. Fixed stop loss and take profit levels may not adapt to changes in market volatility.

#### Strategy Optimization Directions
1. Introduce more technical indicators, such as moving averages and volatility, to assist in judging the strength and direction of trends.
2. Optimize the trigger conditions for the trailing stop, such as adjusting the pullback percentage based on ATR.
3. Adopt more dynamic stop loss and take profit methods, such as trailing stops and stepped take profits.
4. Optimize parameters to find the optimal combination for different markets and instruments.

#### Summary
This strategy captures bull and bear trends through the continuity of candles while setting stop loss and take profit to control risks. The introduction of a trailing stop can better protect profits. However, it may generate frequent signals in choppy markets, requiring further optimization of signal reliability. In addition, the setting of stop loss and take profit can be more flexible to adapt to dynamic market changes. Overall, the strategy has a simple and clear idea, suitable for trending markets, but there is still room for optimization.
[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-04-16 00:00:00
end: 2024-05-16 00:00:00
period: 1h
basePeriod: 15m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

//@version=5
strategy("K Consecutive Candles 數來寶V2", max_bars_back=300, overlay=true)

// 定義用戶輸入
k = input.int(3, title="Number of Consecutive Candles for Long", minval=1)
k2 = input.int(3, title="Number of Consecutive Candles for Short", minval=1)
stopLossTicks = input.int(500, title="Stop Loss (Ticks)")
takeProfitTicks = input.int(500, title="Take Profit (Ticks)")
iTGT = input.int(200,"iTGT")  // 移動停利點
iPcnt = input.int(50,"iPcnt")  // 移動停利%

var float TrailValue = 0
var float TrailExit = 0
var float  vMP = 0

BarsSinceEntry = ta.barssince(strategy.position_size == 0)

vMP := strategy.position_size

// 创建一个包含键值对的字典
addArrayData(type, value) =>
    alert_array = array.new_string()
    array.push(alert_array, '"timenow": ' + str.tostring(timenow))
    array.push(alert_array, '"seqNum": ' + str.tostring(value))
    array.push(alert_array, '"type": "' + type + '"')
    alertstring = '{' + array.join(alert_array,', ') + '}'


// 定義條件變量
var int countLong = 0  // 記錄連續多頭條件成立的次數
var int countShort = 0 // 記錄連續空頭條件成立的次數

// 計算連續大於或小於前一根的收盤價格的次數
if close > close[1]
    countLong += 1
    countShort := 0 // 重置空頭計數
else if close < close[1]
    countShort += 1
    countLong := 0 // 重置多頭計數
else
    countLong := 0
    countShort := 0

// 開設多頭倉位條件
if countLong >= k
    strategy.entry("Long Entry", strategy.long)
    strategy.exit("Exit Long", "Long Entry", loss=stopLossTicks, profit=takeProfitTicks)
    

if vMP>0
    TrailValue := ta.highest(high,BarsSinceEntry)
    TrailExit := TrailValue - iPcnt*0.01*(TrailValue - strategy.position_avg_price)
    if TrailValue > strategy.position_avg_price + iTGT * syminfo.minmove/syminfo.pricescale and close < TrailExit
        
        strategy.close("Long Entry", comment = "Trl_LX"+ str.tostring(close[0]))
// 開設空頭倉位條件
if countShort >= k2
    strategy.entry("Short Entry", strategy.short)
    strategy.exit("Exit Short", "Short Entry", loss=stopLossTicks, profit=takeProfitTicks)

if vMP<0    
    TrailValue := ta.lowest(low,BarsSinceEntry)
    TrailExit := TrailValue - iPcnt*0.01*(TrailValue - strategy.position_avg_price)
    if TrailValue < strategy.position_avg_price - iTGT * syminfo.minmove/syminfo.pricescale and close > TrailExit
        
        strategy.close("short60", comment = "Trl_SX"+ str.tostring(close[0]))





```

> Detail

https://www.fmz.com/strategy/451715

> Last Modified

2024-05-17 13:54:06
