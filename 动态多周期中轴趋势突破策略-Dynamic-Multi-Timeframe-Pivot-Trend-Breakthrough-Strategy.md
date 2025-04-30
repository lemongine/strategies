
> Name

动态多周期中轴趋势突破策略-Dynamic-Multi-Timeframe-Pivot-Trend-Breakthrough-Strategy

> Author

ianzeng123

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/2d8e4dfd81c49caa93d4f.png)
![IMG](https://www.fmz.com/upload/asset/2d8c09bb22b4d833d0b6f.png)




[trans]
#### 概述

本策略是一种基于多周期中轴和相对强弱指数(RSI)的动态趋势突破交易策略。通过结合周线级别的价格支撑和压力位与RSI指标，该策略旨在捕捉金融市场中的趋势性机会，同时提供精细的仓位管理和风险控制机制。

#### 策略原理

策略的核心原理包括以下关键步骤：

1. 多周期价格中枢计算：
- 使用周线级别的前一根K线收盘价、最高价和最低价计算关键支撑压力位
- 计算典型的支撑位(S1、S2、S3)和压力位(R1、R2、R3)
- 通过动态因子调整支撑压力位的灵敏度

2. RSI指标动态优化：
- 采用21周期的RSI指标计算
- 引入指数移动平均线(EMA)平滑RSI
- 构建复合指标，结合RSI原始值和EMA平滑值

3. 交易信号生成：
- 多头入场：复合指标上穿0
- 多头出场：最高价突破R3压力位
- 空头入场：最低价跌破S3支撑位
- 空头出场：复合指标下穿0

#### 策略优势

1. 多周期视角：通过引入周线级别数据，有效过滤短期市场噪音
2. 灵活的仓位管理：分阶段止盈机制，降低单次交易风险
3. 动态指标构建：结合RSI和EMA，提高信号的准确性
4. 对称的多空交易逻辑：为不同市场环境提供灵活策略
5. 风险可控：内置止损和分阶段止盈机制

#### 策略风险

1. 指标滞后性：RSI和价格中枢可能存在滞后problem
2. 参数敏感性：策略表现高度依赖参数选择
3. 交易成本影响：频繁交易可能导致高额手续费
4. 极端市场情况：趋势反转和剧烈波动可能导致策略失效

#### 策略优化方向

1. 引入机器学习算法优化参数选择
2. 增加成交量和波动率过滤机制
3. 结合更多技术指标进行信号验证
4. 开发动态止损和止盈算法
5. 引入更复杂的仓位规模管理模型

#### 总结

该策略通过多周期、多指标的综合分析，构建了一个相对稳健的趋势突破交易方法。其核心优势在于对市场趋势的动态捕捉和精细化的风险管理。未来的优化空间包括算法智能化和风险控制模型的迭代。

||

#### Overview

This strategy is a dynamic trend breakthrough trading approach based on multi-timeframe pivots and the Relative Strength Index (RSI). By combining weekly-level price support and resistance levels with the RSI indicator, the strategy aims to capture trend opportunities in financial markets while providing refined position management and risk control mechanisms.

#### Strategy Principles

The core principles of the strategy include the following key steps:

1. Multi-Timeframe Price Pivot Calculation:
- Calculate key support and resistance levels using weekly-level previous candle's close, high, and low prices
- Compute typical support levels (S1, S2, S3) and resistance levels (R1, R2, R3)
- Dynamically adjust support and resistance levels' sensitivity through a factor

2. RSI Indicator Dynamic Optimization:
- Calculate RSI with a 21-period length
- Introduce Exponential Moving Average (EMA) to smooth RSI
- Construct a composite indicator combining raw RSI and EMA smoothed values

3. Trading Signal Generation:
- Long Entry: Composite indicator crosses above 0
- Long Exit: Highest price breaks R3 resistance level
- Short Entry: Lowest price breaks S3 support level
- Short Exit: Composite indicator crosses below 0

#### Strategy Advantages

1. Multi-Timeframe Perspective: Effectively filter short-term market noise by introducing weekly-level data
2. Flexible Position Management: Staged take-profit mechanism reduces single-trade risk
3. Dynamic Indicator Construction: Combine RSI and EMA to improve signal accuracy
4. Symmetric Long and Short Trading Logic: Provide flexible strategies for different market environments
5. Controllable Risk: Built-in stop-loss and staged take-profit mechanisms

#### Strategy Risks

1. Indicator Lag: RSI and price pivots may have latency issues
2. Parameter Sensitivity: Strategy performance highly depends on parameter selection
3. Transaction Cost Impact: Frequent trading may lead to high commission fees
4. Extreme Market Conditions: Trend reversal and violent fluctuations may cause strategy failure

#### Strategy Optimization Directions

1. Introduce machine learning algorithms to optimize parameter selection
2. Add volume and volatility filtering mechanisms
3. Combine more technical indicators for signal verification
4. Develop dynamic stop-loss and take-profit algorithms
5. Introduce more complex position sizing management models

#### Summary

The strategy builds a relatively robust trend breakthrough trading method through multi-timeframe and multi-indicator comprehensive analysis. Its core advantage lies in dynamically capturing market trends and fine-grained risk management. Future optimization spaces include algorithmic intelligence and iterative risk control model development.
[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-03-31 00:00:00
end: 2025-03-29 08:00:00
period: 1d
basePeriod: 1d
exchanges: [{"eid":"Futures_Binance","currency":"ETH_USDT"}]
*/

// This Pine Script™ code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © yuxishejiang

//@version=6
//@version=5
strategy(title="BTC中轴策略优化-V2", overlay=true, pyramiding=1, initial_capital=5000, default_qty_type=strategy.percent_of_equity, default_qty_value=100, calc_on_order_fills=false, slippage=0, commission_type=strategy.commission.percent, commission_value=0.075)

// 核心参数
strat_dir_input = input.string(title="Strategy Direction", defval="long", options=["long", "short"])
strat_dir_value = strat_dir_input == "long" ? strategy.direction.long : strat_dir_input == "short" ? strategy.direction.short : strategy.direction.all
strategy.risk.allow_entry_in(strat_dir_value)

// 指标计算
higherTF = input.timeframe("W", "Higher Timeframe")
pc = request.security(syminfo.tickerid, higherTF, close[1], barmerge.gaps_off, barmerge.lookahead_on)
ph = request.security(syminfo.tickerid, higherTF, high[1], barmerge.gaps_off, barmerge.lookahead_on)
pl = request.security(syminfo.tickerid, higherTF, low[1], barmerge.gaps_off, barmerge.lookahead_on)

PP = (ph + pl + pc) / 3
R1 = PP + (PP - pl)
S1 = PP - (ph - PP)
R2 = PP + (ph - pl)
S2 = PP - (ph - pl)
factor = input.int(2, "Factor")
R3 = ph + factor * (PP - pl)
S3 = pl - 2 * (ph - PP)

length = input.int(21, "RSI Length")
p = close
vrsi = ta.rsi(p, length)
pp_ema = ta.ema(vrsi, length)
d = (vrsi - pp_ema) * 5
cc = (vrsi + d + pp_ema) / 2

// 仓位管理变量
var float entry_qty = na

// 交易执行逻辑
longEntry = ta.crossover(cc, 0)
longExit = ta.crossover(high, R3)  // 使用实时最高价判断

shortEntry = ta.crossunder(low, S3)  // 改为使用S3支撑位
shortExit = ta.crossunder(cc, 0)     // 同步修改为下穿

if (longEntry)
    strategy.entry("Long", strategy.long)
    entry_qty := strategy.position_size

if (strategy.position_size > 0 and longExit)
    strategy.close("Long", comment="5M背离离场")

if (shortEntry)
    strategy.entry("Short", strategy.short)
    entry_qty := strategy.position_size

if (strategy.position_size < 0 and shortExit)
    strategy.close("Short", comment="空头离场")

// 止盈止损模块
per(pcnt) =>
    strategy.position_size != 0 ? math.round(math.abs(pcnt/100 * strategy.position_avg_price / syminfo.mintick)) : na

stoploss = input.float(15, "Stop Loss (%)", minval=0.01)
tp1 = input.float(3, "Take Profit 1 (%)", minval=0.01)
tp2 = input.float(5, "Take Profit 2 (%)", minval=0.01)
tp3 = input.float(7, "Take Profit 3 (%)", minval=0.01)
tp4 = input.float(10, "Take Profit 4 (%)", minval=0.01)

// 分阶段平仓逻辑
if strategy.position_size != 0
    qty_total = math.abs(entry_qty)
    qty1 = math.floor(qty_total * 0.25)
    qty2 = math.floor(qty_total * 0.25)
    qty3 = math.floor(qty_total * 0.25)
    qty4 = qty_total - (qty1 + qty2 + qty3)
    
    if strategy.position_size > 0
        strategy.exit("x1", qty=qty1, profit=per(tp1), loss=per(stoploss))
        strategy.exit("x2", qty=qty2, profit=per(tp2), loss=per(stoploss))
        strategy.exit("x3", qty=qty3, profit=per(tp3), loss=per(stoploss))
        strategy.exit("x4", qty=qty4, profit=per(tp4), loss=per(stoploss))
    else
        strategy.exit("x1", qty=qty1, profit=per(tp1), loss=per(stoploss))
        strategy.exit("x2", qty=qty2, profit=per(tp2), loss=per(stoploss))
        strategy.exit("x3", qty=qty3, profit=per(tp3), loss=per(stoploss))
        strategy.exit("x4", qty=qty4, profit=per(tp4), loss=per(stoploss))

// 可视化部分保持不变
// 多头入场可视化
if (longEntry)
    label.new(bar_index, low, "多头入场", color=color.green, textcolor=color.white, style=label.style_label_up, size=size.small)

// 多头离场可视化
if (strategy.position_size > 0 and longExit)
    label.new(bar_index, high, "多头离场", color=color.red, textcolor=color.white, style=label.style_label_down, size=size.small)

// 空头入场可视化
if (shortEntry)
    label.new(bar_index, high, "空头入场", color=color.red, textcolor=color.white, style=label.style_label_down, size=size.small)

// 空头离场可视化
if (strategy.position_size < 0 and shortExit)
    label.new(bar_index, low, "空头离场", color=color.green, textcolor=color.white, style=label.style_label_up, size=size.small)

```

> Detail

https://www.fmz.com/strategy/488908

> Last Modified

2025-03-31 17:27:39
