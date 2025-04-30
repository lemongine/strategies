
> Name

均线交叉MACD慢线动量策略Moving-Average-Crossover-MACD-Slow-Line-Momentum-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/142c344c1944b0db157.png)

[trans]
#### 概述
该策略采用了均线交叉和MACD指标作为主要的交易信号。策略以快速均线与多条慢速均线的交叉作为开仓信号,同时结合MACD慢线柱状图的正负作为趋势判断依据。策略在开仓同时设置了多级止盈和止损,并随着持仓时间的增加不断修改止损位置以锁定利润。

#### 策略原理
1. 快速均线与慢速均线1交叉向上,同时收盘价在慢速均线2之上,MACD柱状图大于0,做多;
2. 快速均线与慢速均线1交叉向下,同时收盘价在慢速均线2之下,MACD柱状图小于0,做空;
3. 开仓同时设置多级止盈和止损,止盈位根据风险偏好设置,止损位则随着持仓时间不断调整,逐步锁定利润;
4. 均线周期、MACD参数、止盈止损位等均可灵活调整,以适应不同市场环境。

该策略利用均线交叉捕捉趋势,同时用MACD指标进行方向确认,增强趋势判断的可靠性。多级止盈止损的设置能够更好地控制风险和利润。

#### 策略优势
1. 均线交叉是经典的趋势跟踪方法,能够及时捕捉趋势的形成;
2. 多级均线的使用能够更全面地判断趋势强度和持续性;
3. MACD指标可以有效识别趋势和判断动量,作为均线交叉的有力补充;
4. 多级止盈和动态止损的设置既能控制风险,又能让利润奔跑,增强系统的稳健性;
5. 参数可调,适应性强,可以根据不同品种和周期灵活设置。

#### 策略风险
1. 均线交叉存在信号滞后风险,可能错过早期趋势或追高;
2. 参数设置不当可能导致过度交易或持仓时间过长,增加成本和风险;
3. 止损位设置过于激进可能导致过早止损,止盈位设置过于保守可能影响收益; 
4. 趋势突变或市场异动可能导致策略失效。

这些风险可以通过优化参数、调整仓位、设置额外条件等方式来控制。但任何策略都无法完全规避风险,需要投资者审慎对待。

#### 策略优化方向
1. 可以考虑引入更多指标,如RSI、布林带等,进一步确认趋势和信号;
2. 可以对止盈止损位的设置进行更精细的优化,如考虑ATR或百分比止盈止损;
3. 可以根据市场波动率动态调整参数,提高适应性;
4. 可以引入仓位管理模块,根据风险状况调整仓位大小;
5. 可以对策略进行集合化,建立策略组合来分散风险。

通过不断的优化和改进,可以使策略更加稳健和可靠,更好地适应多变的市场环境。但优化需谨慎,避免过度拟合。

#### 总结
该策略通过均线交叉和MACD指标相结合,构建了一个相对完整的交易系统。多级均线和多头操作的设计增强了系统的趋势捕捉能力和风险控制能力。策略逻辑清晰,便于理解和实现,适合进一步优化和改进。但在实际应用中仍需谨慎,注意控制风险。通过合理的优化和配置,该策略有望成为稳健有效的交易工具。

|| 

#### Overview
This strategy combines moving average crossover and MACD indicator as the main trading signals. It uses the crossover of a fast moving average with multiple slow moving averages as the entry signal, and the positive/negative value of the MACD slow line histogram as the trend confirmation. The strategy sets multiple take-profit and stop-loss levels upon entry, and continuously adjusts the stop-loss level as the holding time increases to lock in profits.

#### Strategy Principle
1. When the fast MA crosses above the slow MA1, the closing price is above the slow MA2, and the MACD histogram is greater than 0, go long;
2. When the fast MA crosses below the slow MA1, the closing price is below the slow MA2, and the MACD histogram is less than 0, go short;
3. Set multiple take-profit and stop-loss levels upon entry. The take-profit levels are based on risk preference, while the stop-loss levels are adjusted continuously as the holding time increases to gradually lock in profits;
4. The periods of moving averages, MACD parameters, take-profit and stop-loss levels, etc., can all be flexibly adjusted to adapt to different market conditions.

This strategy uses MA crossover to capture trends and MACD to confirm the direction, enhancing the reliability of trend judgment. The multiple take-profit and stop-loss design helps to better control risks and profits.

#### Strategy Advantages
1. MA crossover is a classic trend-following method that can timely capture the formation of trends;
2. The use of multiple MAs can more comprehensively judge the strength and persistence of trends;
3. The MACD indicator can effectively identify trends and judge momentum, serving as a strong supplement to MA crossover;
4. The multiple take-profit and dynamic stop-loss design can both control risks and let profits run, enhancing the robustness of the system;
5. The parameters are adjustable and adaptable, and can be flexibly set according to different instruments and timeframes.

#### Strategy Risks
1. MA crossover has the risk of signal lag, which may miss early trends or chase high;
2. Improper parameter settings may lead to overtrading or overly long holding periods, increasing costs and risks;
3. Overly aggressive stop-loss levels may lead to premature stop-outs, while overly conservative take-profit levels may affect returns;
4. Abrupt trend changes or market anomalies may cause the strategy to fail.

These risks can be controlled by optimizing parameters, adjusting positions, setting additional conditions, etc. However, no strategy can completely avoid risks, and investors need to treat it with caution.

#### Strategy Optimization Directions
1. Consider introducing more indicators, such as RSI, Bollinger Bands, etc., to further confirm trends and signals;
2. Conduct more refined optimization on the setting of take-profit and stop-loss levels, such as considering ATR or percentage-based levels;
3. Dynamically adjust parameters based on market volatility to improve adaptability; 
4. Introduce a position sizing module to adjust position sizes based on risk conditions;
5. Ensemble the strategy to establish a strategy portfolio to diversify risks.

Through continuous optimization and improvement, the strategy can become more robust and reliable, better adapting to the changing market environment. But optimization needs to be done with caution to avoid overfitting.

#### Summary
This strategy combines MA crossover and MACD indicators to construct a relatively complete trading system. The design of multiple MAs and multiple operations enhances the system's trend-capturing and risk-control capabilities. The strategy logic is clear and easy to understand and implement, suitable for further optimization and improvement. However, it still needs to be applied with caution in practice, paying attention to risk control. With reasonable optimization and configuration, this strategy has the potential to become a robust and effective trading tool.
[/trans]

> Strategy Arguments



|Argument|Default|Description|
|----|----|----|
|v_input_1|timestamp(2019-01-01T00:00:00+0300)|startDate|
|v_input_2|timestamp(2044-01-01T00:00:00+0300)|finishDate|
|v_input_float_1|5.1|Take Profit1_%|
|v_input_float_2|10.1|Take Profit2_%|
|v_input_float_3|5.1|Stop loss1_%|
|v_input_float_4|0.1|Stop loss2_%|
|v_input_float_5|-5.5|Stop loss3_%|
|v_input_float_6|0.5|QtyClosingPosition1|
|v_input_float_7|0.25|QtyClosingPosition2|
|v_input_int_1|12|(?MA)Fastlength|
|v_input_int_2|54|Slowlength1|
|v_input_int_3|100|Slowlength2|
|v_input_int_4|365|Slowlength3|
|v_input_string_1|0|Fastlength: EMA|SMA|
|v_input_string_2|0|Slowlength1: EMA|SMA|
|v_input_string_3|0|Slowlength2: EMA|SMA|
|v_input_string_4|0|Slowlength3: EMA|SMA|
|v_input_int_5|12|(?MACD)FastMacd|
|v_input_int_6|26|SlowMacd|
|v_input_int_7|9|HistMacd|
|v_input_3_close|0|Source: close|high|low|open|hl2|hlc3|hlcc4|ohlc4|
|v_input_string_5|0|Oscillator MA Type: EMA|SMA|
|v_input_string_6|0|Signal Line MA Type: EMA|SMA|


> Source (PineScript)

``` pinescript
/*backtest
start: 2023-04-06 00:00:00
end: 2024-04-11 00:00:00
period: 1d
basePeriod: 1h
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © maxmirus

//@version=5
strategy("My strategy_Cross_SMA(EMA)+Macd,slow3",overlay=true)
// ver 4
// Date Inputs
startDate     = input(timestamp('2019-01-01T00:00:00+0300'), ''                              , inline='time1',
  tooltip=' Время первого бара расчета стратегии. Первый ордер может быть выставлен на следующем баре после стартового.')
finishDate    = input(timestamp('2044-01-01T00:00:00+0300'), ''                              , inline='time2',
  tooltip=' Время после которого больше не будут размещаться ордера входа в позицию.')

// Calculate start/end date and time condition
time_cond = true

//SMA(EMA) Inputs

fast=input.int(12, title="Fastlength",group="MA")
slow1=input.int(54,title="Slowlength1",group="MA")
slow2=input.int(100, title="Slowlength2",group="MA")
slow3=input.int(365, title="Slowlength3",group="MA")

fastma=input.string(title="Fastlength", defval="EMA",options=["SMA","EMA"],group="MA")
slowma1=input.string(title="Slowlength1", defval="EMA",options=["SMA","EMA"],group="MA")
slowma2=input.string(title="Slowlength2", defval="EMA",options=["SMA","EMA"],group="MA")
slowma3=input.string(title="Slowlength3", defval="EMA",options=["SMA","EMA"],group="MA")

fastlength = fastma == "EMA" ? ta.ema(close, fast) : ta.sma(close, fast)
slowlength1 = slowma1 == "EMA" ? ta.ema(close, slow1) : ta.sma(close, slow1)
slowlength2 = slowma2 == "EMA" ? ta.ema(close, slow2) : ta.sma(close, slow2)
slowlength3 = slowma3 == "EMA" ? ta.ema(close, slow3) : ta.sma(close, slow3)

//Macd Inputs

macdfastline = input.int(12, title="FastMacd",group="MACD")
macdslowline = input.int(26,title="SlowMacd",group="MACD")
macdhistline = input.int(9,title="HistMacd",group="MACD")
src=input(defval=close,title="Source",group="MACD")
sma_source = input.string(title="Oscillator MA Type",  defval="EMA", options=["SMA", "EMA"],group="MACD")
sma_signal = input.string(title="Signal Line MA Type", defval="EMA", options=["SMA", "EMA"],group="MACD")


fast_ma = sma_source == "SMA" ? ta.sma(src, macdfastline) : ta.ema(src, macdfastline)
slow_ma = sma_source == "SMA" ? ta.sma(src, macdslowline) : ta.ema(src, macdslowline)
macd = fast_ma - slow_ma
signal = sma_signal == "SMA" ? ta.sma(macd, macdhistline) : ta.ema(macd, macdhistline)
hist = macd - signal
//fastMACD = ta.ema(close, macdline) - ta.ema(close, signalline)
//signalMACD = ta.ema(MACD, histline)
//histMACD = MACD - aMACD

//EMA Plot

plot(fastlength,title="SMAfast",color=color.blue)
plot(slowlength1,title="SMAslow1",color=color.orange)
plot(slowlength2,title="SMAslow2",color=color.red)
plot(slowlength3,title="SMAslow3",color=color.black)

//Macd plot
//col_macd = input(#2962FF, "MACD Line  ", group="Color Settings", inline="MACD")
//col_signal = input(#FF6D00, "Signal Line  ", group="Color Settings", inline="Signal")
//col_grow_above = input(#26A69A, "Above   Grow", group="Histogram", inline="Above")
//col_fall_above = input(#B2DFDB, "Fall", group="Histogram", inline="Above")
//col_grow_below = input(#FFCDD2, "Below Grow", group="Histogram", inline="Below")
//col_fall_below = input(#FF5252, "Fall", group="Histogram", inline="Below")

//plot(hist, title="Histogram", style=plot.style_columns, color=(hist>=0 ? (hist[1] < hist ? col_grow_above : col_fall_above) : (hist[1] < hist ? col_grow_below : col_fall_below)))
//plot(macd, title="MACD", color=col_macd)
//plot(signal, title="Signal", color=col_signal)

//Take profit
tp1=input.float(5.1,title="Take Profit1_%",step=0.1)/100
tp2=input.float(10.1,title="Take Profit2_%",step=0.1)/100

//Stop loss
sl1=input.float(5.1,title="Stop loss1_%",step=0.1)/100
sl2=input.float(0.1,title="Stop loss2_%",step=0.1)/100
sl3=input.float(-5.5,title="Stop loss3_%", step=0.1)/100

//Qty closing position

Qty1 = input.float(0.5, title="QtyClosingPosition1",step=0.01)
Qty2 = input.float(0.25, title="QtyClosingPosition2",step=0.01)

//Take profit Long and Short

LongTake1=strategy.position_avg_price*(1+tp1)
LongTake2=strategy.position_avg_price*(1+tp2)

ShortTake1=strategy.position_avg_price*(1-tp1)
ShortTake2=strategy.position_avg_price*(1-tp2)

//Plot Levels Take 
plot(strategy.position_size > 0 ? LongTake1 : na,color=color.green,style=plot.style_linebr)
plot(strategy.position_size > 0 ? LongTake2 : na,color=color.green,style=plot.style_linebr)
plot(strategy.position_size < 0 ? ShortTake1 : na,color=color.green,style=plot.style_linebr)
plot(strategy.position_size < 0 ? ShortTake2 : na,color=color.green,style=plot.style_linebr)

//Stop loss long and short

LongStop1=strategy.position_avg_price*(1-sl1)
LongStop2=strategy.position_avg_price*(1-sl2)
LongStop3=strategy.position_avg_price*(1-sl3)
ShortStop1=strategy.position_avg_price*(1+sl1)
ShortStop2=strategy.position_avg_price*(1+sl2)
ShortStop3=strategy.position_avg_price*(1+sl3)
//Stop=strategy.position_avg_price


//Plot Levels Stop
plot(strategy.position_size > 0 ? LongStop1 : na,color=color.red,style=plot.style_linebr)
plot(strategy.position_size > 0 ? LongStop2 : na,color=color.red,style=plot.style_linebr)
plot(strategy.position_size > 0 ? LongStop3 : na,color=color.red,style=plot.style_linebr)
plot(strategy.position_size < 0 ? ShortStop1 : na,color=color.red,style=plot.style_linebr)
plot(strategy.position_size < 0 ? ShortStop2 : na,color=color.red,style=plot.style_linebr)
plot(strategy.position_size < 0 ? ShortStop3 : na,color=color.red,style=plot.style_linebr)


//Entry condition

LongCondition1 = ta.crossover(fastlength, slowlength1)
LongCondition2 = close>slowlength2
LongCondition3 = time_cond
LongCondition4=close>slowlength3
//LongCondition5=slowlength100>slowlength3
LongCondition6 = hist > 0
buy=(LongCondition1 and LongCondition2 and LongCondition3 and LongCondition4 and LongCondition6 ) and strategy.position_size<=0
//longCondition3 = nz(strategy.position_size) == 0//если отсутствует открытая позиция


ShortCondition1 = ta.crossunder(fastlength, slowlength1)
ShortCondition2 = close<slowlength2
ShortCondition3 = time_cond
ShortCondition4=close<slowlength3
//ShortCondition5=slowlength100<slowlength3
ShortCondition6=hist < 0
sell=(ShortCondition1 and ShortCondition2 and ShortCondition3 and ShortCondition4 and ShortCondition6 ) and strategy.position_size>=0



//Strategy entry

strategy.cancel_all(not strategy.position_size)

if(buy)
    strategy.cancel_all()
    strategy.entry("Buy",strategy.long)
if(sell)
    strategy.cancel_all()
    strategy.entry("Sell",strategy.short)
    
//Strategy Long exit    

var int exitCounter=0

exitCounter := not strategy.position_size or strategy.position_size > 0 and strategy.position_size[1] < 0 or strategy.position_size < 0  and strategy.position_size[1] > 0 ? 0:
               strategy.position_size > 0 and strategy.position_size[1]>strategy.position_size?  exitCounter[1] + 1:
               strategy.position_size < 0 and strategy.position_size[1]<strategy.position_size?  exitCounter[1] - 1:
               exitCounter[1]
if strategy.position_size > 0 and strategy.position_size[1]<=0
    strategy.order("Take Long1",strategy.short, qty=math.abs(strategy.position_size*Qty1), limit=LongTake1, oca_name='Long1', oca_type=strategy.oca.cancel)
if strategy.position_size > 0  and strategy.position_size[1]<=0   
    strategy.order("Take Long2",strategy.short, qty=math.abs(strategy.position_size*Qty2), limit=LongTake2, oca_name='Long2', oca_type=strategy.oca.cancel)

    
if strategy.position_size > 0  and strategy.position_size[1]<=0   
    strategy.order("Stop Long1",strategy.short, qty=math.abs(strategy.position_size),stop=LongStop1,oca_name='Long1',oca_type=strategy.oca.cancel)
if ta.change(exitCounter) and exitCounter==1
    strategy.order("Stop Long2",strategy.short, qty=math.abs(strategy.position_size),stop=LongStop2,oca_name='Long2',oca_type=strategy.oca.cancel)
if ta.change(exitCounter) and exitCounter==2
    strategy.order("Stop Long3",strategy.short, qty=math.abs(strategy.position_size),stop=LongStop3)
    
    
    
    
//  Strategy Short exit  
    
    
if strategy.position_size < 0 and strategy.position_size[1]>=0
    strategy.order("Take Short1", strategy.long, qty=math.abs(strategy.position_size*Qty1), limit=ShortTake1, oca_name='Short1', oca_type=strategy.oca.cancel)
if strategy.position_size < 0 and strategy.position_size[1]>=0 
    strategy.order("Take Short2", strategy.long, qty=math.abs(strategy.position_size*Qty2), limit=ShortTake2, oca_name='Short2', oca_type=strategy.oca.cancel)


    
if strategy.position_size < 0 and strategy.position_size[1]>=0
    strategy.order("Stop Short1",strategy.long, qty=math.abs(strategy.position_size),stop=ShortStop1,oca_name='Short1',oca_type=strategy.oca.cancel)
if ta.change(exitCounter) and exitCounter==-1
    strategy.order("Stop Short2",strategy.long, qty=math.abs(strategy.position_size),stop=ShortStop2,oca_name='Short2',oca_type=strategy.oca.cancel)
if ta.change(exitCounter) and exitCounter==-2
    strategy.order("Stop Short3",strategy.long,qty=math.abs(strategy.position_size),stop=ShortStop3)
    


```

> Detail

https://www.fmz.com/strategy/448074

> Last Modified

2024-04-12 17:16:06
