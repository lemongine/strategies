
> Name

趋势捕捉策略-Trend-Catcher-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/a4765b58d5b7d33406.png)

[trans]
#### 概述
趋势捕捉策略是一种利用独特方法检测趋势形成,并在趋势方向上开仓的策略。它通过计算一定范围内最高价和最低价的差值与该范围内所有K线长度之和的比值,得到一个称为"限度"的百分比值。该值越接近100,表示趋势越强。当该值超过设定的限度,并且移动平均线向上时,策略开多单;当该值超过设定的限度,并且移动平均线向下时,策略开空单。开仓后,策略在价格达到一定水平时平掉部分仓位,并将剩余仓位移动到认为趋势结束的点位。

#### 策略原理
1. 计算一定范围内最高价和最低价的差值,以及该范围内所有K线长度之和。
2. 将差值除以K线长度之和,再乘以100得到一个百分比值,称为"限度"。
3. 当限度超过设定值,并且移动平均线向上时,开多单;当限度超过设定值,并且移动平均线向下时,开空单。
4. 开仓后,当价格达到止盈位平掉部分仓位,剩余仓位移动到止损位。
5. 当移动平均线向下穿越时,平掉多单;当移动平均线向上穿越时,平掉空单。

#### 策略优势
1. 策略使用独特的方法检测趋势形成,通过计算限度值来判断趋势强度,有助于在趋势初期就开仓。
2. 策略在开仓后,通过平掉部分仓位和移动剩余仓位的止损位来控制风险。
3. 策略使用移动平均线的向上和向下穿越来判断趋势结束,有助于及时平仓。

#### 策略风险
1. 策略在趋势初期开仓,如果趋势不能持续,可能会造成损失。
2. 策略使用固定的止盈和止损位,在某些情况下可能不够灵活。
3. 策略只使用了移动平均线来判断趋势,可能会错过一些趋势机会。

#### 策略优化方向
1. 可以考虑使用其他指标来辅助判断趋势,如MACD、RSI等,以提高开仓的准确性。
2. 可以根据市场波动性来动态调整止盈和止损位,以更好地控制风险。
3. 可以考虑在趋势确认后再开仓,以降低趋势初期的风险。

#### 总结
趋势捕捉策略使用独特的方法来检测趋势形成,并在趋势方向上开仓。它通过计算限度值来判断趋势强度,使用移动平均线的穿越来判断趋势结束。策略在开仓后通过平掉部分仓位和移动止损位来控制风险。但是,策略在趋势初期开仓可能面临一定风险,使用固定的止盈止损位可能不够灵活,只使用移动平均线判断趋势可能会错过一些机会。未来可以考虑引入其他指标、动态调整止盈止损位、在趋势确认后再开仓等方式来优化策略。

|| 

#### Overview
The Trend Catcher Strategy is a strategy that detects trend formations using its own unique method and opens positions in the direction of the trend. It calculates a percentage value called the "limit" by dividing the difference between the highest and lowest prices in a certain range by the sum of the lengths of the candles in that range. The closer this value is to 100, the stronger the trend. When this value exceeds a set limit and the moving average is rising, the strategy opens a long position; when this value exceeds a set limit and the moving average is falling, the strategy opens a short position. After opening a position, the strategy closes a part of the position when the price reaches a certain level and moves the remaining position to a point where it believes the trend is over.

#### Strategy Principle
1. Calculate the difference between the highest and lowest prices in a certain range, as well as the sum of the lengths of all candles in that range.
2. Divide the difference by the sum of the candle lengths and multiply by 100 to get a percentage value called the "limit".
3. When the limit exceeds a set value and the moving average is rising, open a long position; when the limit exceeds a set value and the moving average is falling, open a short position.
4. After opening a position, close a part of the position when the price reaches the take profit level and move the remaining position to the stop loss level.
5. When the moving average crosses downward, close the long position; when the moving average crosses upward, close the short position.

#### Strategy Advantages
1. The strategy uses a unique method to detect trend formations. By calculating the limit value to determine the strength of the trend, it helps to open positions at the beginning of the trend.
2. After opening a position, the strategy controls risk by closing a part of the position and moving the stop loss level of the remaining position.
3. The strategy uses the upward and downward crossings of the moving average to determine the end of the trend, which helps to close positions in a timely manner.

#### Strategy Risks
1. The strategy opens positions at the beginning of the trend. If the trend cannot be sustained, it may cause losses.
2. The strategy uses fixed take profit and stop loss levels, which may not be flexible enough in some cases.
3. The strategy only uses the moving average to determine trends, which may miss some trend opportunities.

#### Strategy Optimization Direction
1. Consider using other indicators such as MACD and RSI to assist in determining trends and improve the accuracy of opening positions.
2. Dynamically adjust take profit and stop loss levels based on market volatility to better control risk.
3. Consider opening positions only after the trend is confirmed to reduce risks at the beginning of the trend.

#### Summary
The Trend Catcher Strategy uses a unique method to detect trend formations and opens positions in the direction of the trend. It calculates the limit value to determine the strength of the trend and uses the crossing of the moving average to determine the end of the trend. The strategy controls risk by closing a part of the position and moving the stop loss level after opening a position. However, the strategy may face certain risks when opening positions at the beginning of the trend, using fixed take profit and stop loss levels may not be flexible enough, and only using the moving average to determine trends may miss some opportunities. In the future, we can consider introducing other indicators, dynamically adjusting take profit and stop loss levels, and opening positions only after the trend is confirmed to optimize the strategy.

[/trans]

> Strategy Arguments



|Argument|Default|Description|
|----|----|----|
|v_input_int_1|10|len|
|v_input_float_1|2.5|tp|
|v_input_float_2|2.5|sl|
|v_input_int_2|5|malen|
|v_input_int_3|50|limit|
|v_input_int_4|50|qty_balance|


> Source (PineScript)

``` pinescript
/*backtest
start: 2023-04-20 00:00:00
end: 2024-04-25 00:00:00
period: 1d
basePeriod: 1h
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © faytterro

//@version=5
strategy("Trend Catcher Strategy", overlay=true, default_qty_type = strategy.percent_of_equity, default_qty_value = 100)
len = input.int(10)
tp = input.float(2.5, step = 0.1)
sl = input.float(2.5, step = 0.1)
malen = input.int(5)
limit = input.int(50)
ma = ta.sma(close,malen)
sum = 0.0
for i = 0 to len-1
    sum := sum + high[i]-low[i]
frs = 100*(ta.highest(high,len)-ta.lowest(low,len))/sum
//hline(50)
//plot(frs, color = color.white)
l = ta.crossover(frs,limit) and ma>ma[1]
s = ta.crossover(frs,limit) and ma<ma[1]
cl = ma<ma[1]
cs = ma>ma[1]
qty_balance=input.int(50, maxval = 100)
if (l)
    strategy.entry("My Long Entry Id", strategy.long)
    strategy.exit("exit long", "My Long Entry Id", qty_percent = qty_balance, limit = close*(100+tp)/100, stop = close*(100-sl)/100)

if (s)
    strategy.entry("My Short Entry Id", strategy.short)
    strategy.exit("exit short", "My Short Entry Id", qty_percent = qty_balance, limit = close*(100-tp)/100, stop = close*(100+sl)/100)

if (cl)
    strategy.close("My Long Entry Id")
if (cs)
    strategy.close("My Short Entry Id")

l:= l and strategy.opentrades<1
s:= s and strategy.opentrades<1
transp = strategy.opentrades>0? 0 : 100
pma=plot(ma, color = ma<ma[1]? color.rgb(255, 82, 82, transp) : color.rgb(76, 175, 79, transp))
price = open/2+close/2
pprice = plot(price, display = display.none)
fill(pma,pprice, color = ma<ma[1]? color.rgb(255, 82, 82, transp+90) : color.rgb(76, 175, 79, transp+90))

spm=plot(ta.valuewhen(s,close,0), color = (strategy.opentrades>0 and ma<ma[1] and ma[1]<ma[2])? color.white : color.rgb(1,1,1,100), offset=1)
lpm=plot(ta.valuewhen(l,close,0), color = (strategy.opentrades>0 and ma>ma[1] and ma[1]>ma[2])? color.white : color.rgb(1,1,1,100), offset=1)

ltp=plot(ta.valuewhen(l,close,0)*(100+ta.valuewhen(l,tp,0))/100,  color = (strategy.opentrades>0 and ma>ma[1] and ma[1]>ma[2])? color.green : color.rgb(1,1,1,100), offset=1)
lsl=plot(ta.valuewhen(l,close,0)*(100-ta.valuewhen(l,sl,0))/100,  color = (strategy.opentrades>0 and ma>ma[1] and ma[1]>ma[2])? color.red : color.rgb(1,1,1,100), offset=1)

stp=plot(ta.valuewhen(s,close,0)*(100-ta.valuewhen(s,tp,0))/100, color = (strategy.opentrades>0 and ma<ma[1] and ma[1]<ma[2])? color.green : color.rgb(1,1,1,100), offset=1)
ssl=plot(ta.valuewhen(s,close,0)*(100+ta.valuewhen(s,sl,0))/100, color = (strategy.opentrades>0 and ma<ma[1] and ma[1]<ma[2])? color.red : color.rgb(1,1,1,100), offset=1)
fill(stp,spm, color = (strategy.opentrades>0 and ma<ma[1] and ma[1]<ma[2])? color.rgb(76, 175, 79, 90) : color.rgb(1,1,1,100))
fill(ssl,spm, color = (strategy.opentrades>0 and ma<ma[1] and ma[1]<ma[2])? color.rgb(255, 82, 82, 90) : color.rgb(1,1,1,100))
fill(ltp,lpm, color = (strategy.opentrades>0 and ma>ma[1] and ma[1]>ma[2])? color.rgb(76, 175, 79, 90) : color.rgb(1,1,1,100))
fill(lsl,lpm, color = (strategy.opentrades>0 and ma>ma[1] and ma[1]>ma[2])? color.rgb(255, 82, 82, 90) : color.rgb(1,1,1,100))
```

> Detail

https://www.fmz.com/strategy/449507

> Last Modified

2024-04-26 11:48:28
