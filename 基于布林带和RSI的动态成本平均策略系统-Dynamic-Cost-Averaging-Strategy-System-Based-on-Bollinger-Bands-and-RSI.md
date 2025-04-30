
> Name

基于布林带和RSI的动态成本平均策略系统-Dynamic-Cost-Averaging-Strategy-System-Based-on-Bollinger-Bands-and-RSI

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/c34b2567b90dd65450.png)

[trans]
#### 概述
该策略是一个结合了布林带(Bollinger Bands)、相对强弱指标(RSI)和动态成本平均(DCA)的量化交易系统。策略通过设定资金管理规则,在市场波动中自动执行分批建仓操作,同时结合技术指标进行买卖信号判断,实现风险可控的交易执行。系统还包含了止盈逻辑和累计利润跟踪功能,可以有效监控和管理交易表现。

#### 策略原理
策略主要基于以下几个核心组件运作:
1. 布林带指标用于判断价格波动区间,当价格触及下轨时考虑买入,触及上轨时考虑卖出
2. RSI指标用于确认市场超买超卖状态,RSI低于25时确认超卖,高于75时确认超卖
3. DCA模块根据账户权益动态计算每次建仓金额,实现资金的自适应管理
4. 止盈模块设置5%的获利目标,达到目标自动平仓保护利润
5. 市场状态监控模块计算90天市场变化幅度,帮助判断整体趋势
6. 累计利润跟踪模块记录每笔交易的盈亏状况,方便评估策略绩效

#### 策略优势
1. 结合多重技术指标交叉验证,提高信号可靠性
2. 采用动态仓位管理,避免固定仓位带来的风险
3. 设置合理止盈条件,及时锁定利润
4. 具备市场趋势监控功能,便于把握大局
5. 完善的利润跟踪系统,便于分析策略表现
6. 警报功能配置完善,可实时提醒交易机会

#### 策略风险
1. 震荡市场可能频繁触发信号导致交易成本增加
2. RSI指标在趋势市场可能产生滞后
3. 固定百分比止盈可能在强趋势市场过早退出
4. DCA策略在单边下跌市场可能造成较大回撤
建议采取以下措施管理风险:
- 设置最大持仓限制
- 根据市场波动度动态调整参数
- 增加趋势过滤器
- 实施分级止盈策略

#### 策略优化方向
1. 参数动态优化:
- 布林带参数可根据波动率自适应调整
- RSI阈值可随市场周期变化
- DCA资金比例可跟随账户规模调整

2. 信号系统增强:
- 增加成交量确认
- 添加趋势线分析
- 结合更多技术指标交叉验证

3. 风险控制完善:
- 实现动态止损
- 添加最大回撤控制
- 设置每日亏损限制

#### 总结
该策略通过综合运用技术分析和资金管理方法,构建了一个较为完整的交易系统。策略的优势在于多重信号确认和完善的风险管理,但仍需要在实盘中进行充分测试和优化。通过持续改进参数设置和增加辅助指标,该策略有望在实际交易中取得稳定表现。

|| 

#### Overview
This strategy is a quantitative trading system that combines Bollinger Bands, Relative Strength Index (RSI), and Dynamic Cost Averaging (DCA). The strategy implements automatic position building through established money management rules during market fluctuations, while integrating technical indicators for buy/sell signal determination to achieve controlled risk execution. The system also includes take-profit logic and cumulative profit tracking functionality for effective monitoring and management of trading performance.

#### Strategy Principles
The strategy operates based on the following core components:
1. Bollinger Bands for determining price volatility ranges, considering buying at lower band and selling at upper band
2. RSI for confirming overbought/oversold conditions, confirming oversold below 25 and overbought above 75
3. DCA module dynamically calculates position sizes based on account equity for adaptive capital management
4. Take-profit module sets 5% profit target for automatic position closing
5. Market state monitoring calculates 90-day market changes to assess overall trends
6. Cumulative profit tracking records each trade's profit/loss for strategy performance evaluation

#### Strategy Advantages
1. Multiple technical indicator cross-validation improves signal reliability
2. Dynamic position management avoids fixed-position risks
3. Reasonable take-profit conditions secure timely profits
4. Market trend monitoring capabilities aid in big-picture understanding
5. Comprehensive profit tracking system facilitates strategy analysis
6. Well-configured alert system provides real-time trading opportunities

#### Strategy Risks
1. Choppy markets may trigger frequent signals increasing trading costs
2. RSI indicators may lag in trending markets
3. Fixed percentage take-profit may exit too early in strong trends
4. DCA strategy may cause significant drawdowns in prolonged downtrends
Risk management recommendations:
- Set maximum position limits
- Dynamically adjust parameters based on market volatility
- Add trend filters
- Implement tiered take-profit strategy

#### Strategy Optimization Directions
1. Parameter Dynamic Optimization:
- Bollinger Bands parameters adapt to volatility
- RSI thresholds vary with market cycles
- DCA allocation adjusts with account size

2. Signal System Enhancement:
- Add volume confirmation
- Include trendline analysis
- Integrate additional technical indicator cross-validation

3. Risk Control Improvement:
- Implement dynamic stop-loss
- Add maximum drawdown control
- Set daily loss limits

#### Summary
The strategy builds a comprehensive trading system through combined technical analysis and money management methods. Its strengths lie in multiple signal confirmation and thorough risk management, though it still requires extensive testing and optimization in live trading. Through continuous improvement in parameter settings and additional auxiliary indicators, the strategy shows promise for stable performance in actual trading.
[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2023-11-27 00:00:00
end: 2024-11-26 00:00:00
period: 1d
basePeriod: 1d
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
*/

//@version=5
strategy("Combined BB RSI with Cumulative Profit, Market Change, and Futures Strategy (DCA)", shorttitle="BB RSI Combined DCA Strategy", overlay=true)

// Input Parameters
length = input.int(20, title="BB Length")  // Adjusted BB length
mult = input.float(2.5, title="BB Multiplier")  // Adjusted BB multiplier
rsiLength = input.int(14, title="RSI Length")  // Adjusted RSI length
rsiBuyLevel = input.int(25, title="RSI Buy Level")  // Adjusted RSI Buy Level
rsiSellLevel = input.int(75, title="RSI Sell Level")  // Adjusted RSI Sell Level
dcaPositionSizePercent = input.float(1, title="DCA Position Size (%)", tooltip="Percentage of equity to use in each DCA step")
takeProfitPercentage = input.float(5, title="Take Profit (%)", tooltip="Take profit percentage for DCA strategy")

// Calculate DCA position size
equity = strategy.equity  // Account equity
dcaPositionSize = (equity * dcaPositionSizePercent) / 100  // DCA position size as percentage of equity

// Bollinger Bands Calculation
basis = ta.sma(close, length)
dev = mult * ta.stdev(close, length)
upper = basis + dev
lower = basis - dev

// RSI Calculation
rsi = ta.rsi(close, rsiLength)

// Plotting Bollinger Bands and RSI levels
plot(upper, color=color.red, title="Bollinger Upper")
plot(lower, color=color.green, title="Bollinger Lower")
hline(rsiBuyLevel, "RSI Buy Level", color=color.green)
hline(rsiSellLevel, "RSI Sell Level", color=color.red)

// Buy and Sell Signals
buySignal = (rsi < rsiBuyLevel and close <= lower)
sellSignal = (rsi > rsiSellLevel and close >= upper)

// DCA Strategy: Enter Long or Short based on signals with calculated position size
if (buySignal)
    strategy.entry("DCA Buy", strategy.long)

if (sellSignal)
    strategy.entry("DCA Sell", strategy.short)

// Take Profit Logic
if (strategy.position_size > 0)  // If long
    strategy.exit("Take Profit Long", from_entry="DCA Buy", limit=close * (1 + takeProfitPercentage / 100))

if (strategy.position_size < 0)  // If short
    strategy.exit("Take Profit Short", from_entry="DCA Sell", limit=close * (1 - takeProfitPercentage / 100))

// Plot Buy/Sell Signals on the chart
plotshape(buySignal, title="Buy Signal", location=location.belowbar, color=color.green, style=shape.labelup, text="BUY", textcolor=color.white)
plotshape(sellSignal, title="Sell Signal", location=location.abovebar, color=color.red, style=shape.labeldown, text="SELL", textcolor=color.white)

// Alerts for Buy/Sell Signals
alertcondition(buySignal, title="Buy Alert", message="Buy Signal Detected")
alertcondition(sellSignal, title="Sell Alert", message="Sell Signal Detected")

// Cumulative Profit Calculation
var float buyPrice = na
var float profit = na
var float cumulativeProfit = 0.0  // Cumulative profit tracker

if (buySignal)
    buyPrice := close
if (sellSignal and not na(buyPrice))
    profit := (close - buyPrice) / buyPrice * 100
    cumulativeProfit := cumulativeProfit + profit  // Update cumulative profit
    label.new(bar_index, high, text="P: " + str.tostring(profit, "#.##") + "%", color=color.blue, style=label.style_label_down)
    buyPrice := na  // Reset buyPrice after sell

// Plot cumulative profit on the chart
var label cumulativeLabel = na
if (not na(cumulativeProfit))
    if not na(cumulativeLabel)
        label.delete(cumulativeLabel)
    cumulativeLabel := label.new(bar_index, high + 10, text="Cumulative Profit: " + str.tostring(cumulativeProfit, "#.##") + "%", color=color.purple, style=label.style_label_up)

// Market Change over 3 months Calculation
threeMonthsBars = 3 * 30 * 24  // Approximation of 3 months in bars (assuming 1 hour per bar)
priceThreeMonthsAgo = request.security(syminfo.tickerid, "D", close[threeMonthsBars])
marketChange = (close - priceThreeMonthsAgo) / priceThreeMonthsAgo * 100

// Plot market change over 3 months
var label marketChangeLabel = na
if (not na(marketChange))
    if not na(marketChangeLabel)
        label.delete(marketChangeLabel)
    marketChangeLabel := label.new(bar_index, high + 20, text="Market Change (3 months): " + str.tostring(marketChange, "#.##") + "%", color=color.orange, style=label.style_label_up)

// Both labels (cumulative profit and market change) are displayed simultaneously
var label infoLabel = na
if (not na(cumulativeProfit) and not na(marketChange))
    if not na(infoLabel)
        label.delete(infoLabel)
    infoLabel := label.new(bar_index, high + 30, text="Cumulative Profit: " + str.tostring(cumulativeProfit, "#.##") + "% | Market Change (3 months): " + str.tostring(marketChange, "#.##") + "%", color=color.purple, style=label.style_label_upper_right)

```

> Detail

https://www.fmz.com/strategy/473153

> Last Modified

2024-11-27 16:37:12
