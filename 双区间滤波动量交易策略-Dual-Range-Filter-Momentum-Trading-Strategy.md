
> Name

双区间滤波动量交易策略-Dual-Range-Filter-Momentum-Trading-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/e043de80898806e175.png)

[trans]
#### 概述
该策略是一个基于双区间滤波器的动量交易策略。策略通过计算快速和慢速两个周期的平滑区间,得到一个综合的区间滤波器,用于判断当前价格的走势。当价格上穿/下穿该区间时,策略会产生买入/卖出信号。同时,该策略还设置了四个梯度止盈和一个止损,用于控制风险和锁定利润。

#### 策略原理
1. 计算快速和慢速两个周期的平滑区间。快速区间使用较短的周期和较小的倍数,慢速区间使用较长的周期和较大的倍数。
2. 将快速和慢速区间的均值作为综合区间滤波器(TRF)。
3. 计算当前价格与上一个价格的关系,判断上升趋势(upward)和下降趋势(downward)。
4. 计算动态上轨(FUB)和下轨(FLB),作为趋势的参考。
5. 根据收盘价与TRF的关系,产生买入和卖出信号。
6. 设置四个梯度止盈和一个止损,对应不同的仓位比例和获利/亏损百分比。

#### 优势分析
1. 双区间滤波器结合了快速和慢速两种周期,能够适应不同的市场节奏,捕捉更多的交易机会。
2. 动态上下轨的设计有助于顺应当前趋势,减少虚假信号。
3. 四个梯度止盈的设置可以在趋势延续时获得更多利润,同时也能在趋势反转时及时锁定部分盈利。
4. 止损的设置有助于控制单笔交易的最大亏损,保护账户安全。

#### 风险分析
1. 当市场出现震荡或者区间行情时,该策略可能会产生较多的虚假信号,导致频繁交易和手续费损失。
2. 梯度止盈的设置可能会导致部分利润被提前锁定,无法完全享受趋势行情的收益。
3. 止损的设置可能无法完全避免黑天鹅事件带来的极端损失。

#### 优化方向
1. 可以考虑引入更多的技术指标或者市场情绪指标,作为趋势判断的辅助条件,减少虚假信号。
2. 对于止盈和止损的设置,可以根据不同的市场环境和交易品种进行动态调整,提高策略的适应性。
3. 在回测的基础上,可以进一步优化参数设置,如快速和慢速区间的周期选择、止盈和止损的百分比设置等,提高策略的稳定性和盈利能力。

#### 总结
双区间滤波动量交易策略通过快慢两个周期的平滑区间构建综合滤波器,同时结合动态上下轨,对价格走势进行判断,产生买卖信号。策略还设置了四个梯度止盈和一个止损,用于控制风险和锁定利润。该策略适合在趋势行情中使用,但在震荡市场中可能会产生较多虚假信号。未来可以考虑引入更多指标、优化止盈止损设置、动态调整参数等方式,提高策略的适应性和稳定性。

|| 

#### Overview
This strategy is a momentum trading strategy based on a dual range filter. The strategy calculates smooth ranges for fast and slow periods to obtain a comprehensive range filter, which is used to determine the current price trend. When the price crosses above/below this range, the strategy generates buy/sell signals. Additionally, the strategy sets four gradient take-profit levels and one stop-loss level to control risk and lock in profits.

#### Strategy Principle
1. Calculate smooth ranges for fast and slow periods. The fast range uses a shorter period and a smaller multiple, while the slow range uses a longer period and a larger multiple.
2. Use the average of the fast and slow ranges as the comprehensive range filter (TRF).
3. Determine upward and downward trends by comparing the current price with the previous price.
4. Calculate dynamic upper (FUB) and lower (FLB) bands as references for the trend.
5. Generate buy and sell signals based on the relationship between the closing price and TRF.
6. Set four gradient take-profit levels and one stop-loss level, corresponding to different position percentages and profit/loss percentages.

#### Advantage Analysis
1. The dual range filter combines fast and slow periods, enabling the strategy to adapt to different market paces and capture more trading opportunities.
2. The design of dynamic upper and lower bands helps the strategy align with the current trend and reduces false signals.
3. The four gradient take-profit levels allow the strategy to secure more profits when the trend continues while locking in partial gains when the trend reverses.
4. The stop-loss setting helps control the maximum loss per trade and protects account safety.

#### Risk Analysis
1. During market fluctuations or range-bound conditions, the strategy may generate many false signals, leading to frequent trading and commission losses.
2. The gradient take-profit settings may cause some profits to be locked in prematurely, preventing the strategy from fully benefiting from trend movements.
3. The stop-loss setting may not completely avoid extreme losses caused by black swan events.

#### Optimization Direction
1. Consider incorporating more technical indicators or market sentiment indicators as auxiliary conditions for trend determination to reduce false signals.
2. For take-profit and stop-loss settings, dynamically adjust them according to different market environments and trading instruments to improve the strategy's adaptability.
3. Based on backtesting results, further optimize parameter settings, such as the selection of fast and slow range periods, and the percentage settings for take-profit and stop-loss levels, to enhance the strategy's stability and profitability.

#### Summary
The dual range filter momentum trading strategy constructs a comprehensive filter using smooth ranges from fast and slow periods, combined with dynamic upper and lower bands to determine price trends and generate buy/sell signals. The strategy also sets four gradient take-profit levels and one stop-loss level to control risk and lock in profits. This strategy is suitable for use in trending markets but may generate more false signals in fluctuating markets. In the future, consider introducing more indicators, optimizing take-profit and stop-loss settings, and dynamically adjusting parameters to improve the strategy's adaptability and stability.
[/trans]

> Strategy Arguments



|Argument|Default|Description|
|----|----|----|
|v_input_string_1|0|İşlem Yönü: Alis|Satis|Tum|
|v_input_int_1|true|İlk ay|
|v_input_int_2|true|İlk Gün|
|v_input_int_3|2023|İlk Yil|
|v_input_int_4|true|Son Ay|
|v_input_int_5|true|Son Gün|
|v_input_int_6|9999|Son Yıl|
|v_input_1_close|0|Source: close|high|low|open|hl2|hlc3|hlcc4|ohlc4|
|v_input_2|true|Show Buy/Sell Signals ?|
|v_input_int_7|27|Fast period|
|v_input_float_1|1.6|Fast range|
|v_input_int_8|55|Slow period|
|v_input_float_2|2|Slow range|
|v_input_3|true|Mum Renk Ayarları?|
|v_input_4|true|Trend Bazlı Mum Rengi Değişimi?|
|v_input_float_3|100|Zarar Kes Yüzdesi|
|v_input_int_9|5|Satış Lot Sayısı 1.Kısım %|
|v_input_int_10|8|Satış Lot Sayısı 2.Kısım %|
|v_input_int_11|13|Satış Lot Sayısı 3.Kısım %|
|v_input_int_12|21|Satış Lot Sayısı 4.Kısım %|
|v_input_float_4|13|Kar Yüzdesi 1.Kısım|
|v_input_float_5|21|Kar Yüzdesi 2.Kısım|
|v_input_float_6|29|Kar Yüzdesi 3.Kısım|
|v_input_float_7|34|Kar Yüzdesi 4.Kısım|


> Source (PineScript)

``` pinescript
/*backtest
start: 2024-03-01 00:00:00
end: 2024-03-31 23:59:59
period: 1h
basePeriod: 15m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
//@version=5
strategy(title='2"Twin Range Filter', overlay=true)
strat_dir_input = input.string(title='İşlem Yönü', defval='Alis', options=['Alis', 'Satis', 'Tum'])
strat_dir_value = strat_dir_input == 'Alis' ? strategy.direction.long : strat_dir_input == 'Satis' ? strategy.direction.short : strategy.direction.all
strategy.risk.allow_entry_in(strat_dir_value)

////////////////////////////

// Backtest inputs
BaslangicAy = input.int(defval=1, title='İlk ay', minval=1, maxval=12)
BaslangicGun = input.int(defval=1, title='İlk Gün', minval=1, maxval=31)
BaslangicYil = input.int(defval=2023, title='İlk Yil', minval=2000)
SonAy = input.int(defval=1, title='Son Ay', minval=1, maxval=12)
SonGun = input.int(defval=1, title='Son Gün', minval=1, maxval=31)
SonYil = input.int(defval=9999, title='Son Yıl', minval=2000)

start = timestamp(BaslangicYil, BaslangicAy, BaslangicGun, 00, 00)  // backtest start window
finish = timestamp(SonYil, SonAy, SonGun, 23, 59)  // backtest finish window
window() => true

source = input(defval=close, title='Source')
showsignals = input(title='Show Buy/Sell Signals ?', defval=true)
per1 = input.int(defval=27, minval=1, title='Fast period')
mult1 = input.float(defval=1.6, minval=0.1, title='Fast range')
per2 = input.int(defval=55, minval=1, title='Slow period')
mult2 = input.float(defval=2, minval=0.1, title='Slow range')
smoothrng(x, t, m) =>
    wper = t * 2 - 1
    avrng = ta.ema(math.abs(x - x[1]), t)
    smoothrng = ta.ema(avrng, wper) * m
    smoothrng
smrng1 = smoothrng(source, per1, mult1)
smrng2 = smoothrng(source, per2, mult2)
smrng = (smrng1 + smrng2) / 2
rngfilt(x, r) =>
    rngfilt = x
    rngfilt := x > nz(rngfilt[1]) ? x - r < nz(rngfilt[1]) ? nz(rngfilt[1]) : x - r : x + r > nz(rngfilt[1]) ? nz(rngfilt[1]) : x + r
    rngfilt
filt = rngfilt(source, smrng)
upward = 0.0
upward := filt > filt[1] ? nz(upward[1]) + 1 : filt < filt[1] ? 0 : nz(upward[1])
downward = 0.0
downward := filt < filt[1] ? nz(downward[1]) + 1 : filt > filt[1] ? 0 : nz(downward[1])
STR = filt + smrng
STS = filt - smrng
FUB = 0.0
FUB := STR < nz(FUB[1]) or close[1] > nz(FUB[1]) ? STR : nz(FUB[1])
FLB = 0.0
FLB := STS > nz(FLB[1]) or close[1] < nz(FLB[1]) ? STS : nz(FLB[1])
TRF = 0.0
TRF := nz(TRF[1]) == FUB[1] and close <= FUB ? FUB : nz(TRF[1]) == FUB[1] and close >= FUB ? FLB : nz(TRF[1]) == FLB[1] and close >= FLB ? FLB : nz(TRF[1]) == FLB[1] and close <= FLB ? FUB : FUB
al = ta.crossover(close, TRF)
sat = ta.crossunder(close, TRF)
plotshape(showsignals and al, title='Long', text='BUY', style=shape.labelup, textcolor=color.white, size=size.tiny, location=location.belowbar, color=color.rgb(0, 19, 230))
plotshape(showsignals and sat, title='Short', text='SELL', style=shape.labeldown, textcolor=color.white, size=size.tiny, location=location.abovebar, color=color.rgb(0, 19, 230))
alertcondition(al, title='Long', message='Long')
alertcondition(sat, title='Short', message='Short')
Trfff = plot(TRF)
mPlot = plot(ohlc4, title='', style=plot.style_circles, linewidth=0)
longFillColor = close > TRF ? color.green : na
shortFillColor = close < TRF ? color.red : na
fill(mPlot, Trfff, title='UpTrend Highligter', color=longFillColor, transp=90)
fill(mPlot, Trfff, title='DownTrend Highligter', color=shortFillColor, transp=90)

//////////////////////



renk1 = input(true, "Mum Renk Ayarları?")
mumrenk = input(true,title="Trend Bazlı Mum Rengi Değişimi?")
htaColor = renk1 ? (al ? color.rgb(224, 230, 57) : #E56337) : #c92626
barcolor(color = mumrenk ? (renk1 ? htaColor : na) : na)
if (al) and window()
    strategy.entry("Al", strategy.long)
if (sat) and window()
    strategy.entry("Sat", strategy.short)


per1(pcnt) =>
    strategy.position_size != 0 ? math.round(pcnt / 100 * strategy.position_avg_price / syminfo.mintick) : float(na)
zarkesmgb = input.float(title='Zarar Kes Yüzdesi', defval=100, minval=0.01)
zarkeslos = per1(zarkesmgb)
q1 = input.int(title='Satış Lot Sayısı 1.Kısım %', defval=5, minval=1)
q2 = input.int(title='Satış Lot Sayısı 2.Kısım %', defval=8, minval=1)
q3 = input.int(title='Satış Lot Sayısı 3.Kısım %', defval=13, minval=1)
q4 = input.int(title='Satış Lot Sayısı 4.Kısım %', defval=21, minval=1)
tp1 = input.float(title='Kar Yüzdesi 1.Kısım', defval=13, minval=0.01)
tp2 = input.float(title='Kar Yüzdesi 2.Kısım', defval=21, minval=0.01)
tp3 = input.float(title='Kar Yüzdesi 3.Kısım', defval=29, minval=0.01)
tp4 = input.float(title='Kar Yüzdesi 4.Kısım', defval=34, minval=0.01)
strategy.exit('✨KS1', qty_percent=q1, profit=per1(tp1), loss=zarkeslos)
strategy.exit('✨KS2', qty_percent=q2, profit=per1(tp2), loss=zarkeslos)
strategy.exit('✨KS3', qty_percent=q3, profit=per1(tp3), loss=zarkeslos)
strategy.exit('✨KS4', qty_percent=q4, profit=per1(tp4), loss=zarkeslos)


```

> Detail

https://www.fmz.com/strategy/446755

> Last Modified

2024-04-01 10:54:47
