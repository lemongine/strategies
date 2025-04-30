
> Name

多指标加权智能交易策略-Multi-Indicator-Weighted-Smart-Trading-Strategy

> Author

ianzeng123

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/2d973df9d5ce968fe7cde.png)
![IMG](https://www.fmz.com/upload/asset/2d8c7b8ddf785489fbc59.png)



[trans]
#### 概述
多指标加权智能交易策略是一种综合性的量化交易系统，它通过整合多个技术指标的信号并赋予不同权重来生成交易决策。该策略结合了MACD、随机RSI、EMA、超级趋势和移动平均线交叉等多种技术分析工具，形成了一个全面的交易框架。系统不仅支持多级止盈和动态止损机制，还能根据市场状况自动调整交易参数，使其在不同市场环境下都能保持较高的适应性。该策略特别适合中长期交易者，通过权重分配系统使交易决策更加稳健和可靠。

#### 策略原理
该策略的核心在于其加权信号系统，通过五个不同的子策略来生成交易信号：

1. **MACD策略**：利用MACD线与信号线的交叉来确定市场趋势方向。当MACD线上穿信号线时产生买入信号，下穿时产生卖出信号。

2. **随机RSI策略**：结合RSI和随机指标的优势，监测市场的超买超卖状态。当随机RSI低于设定的超卖阈值时产生买入信号，高于超买阈值时产生卖出信号。

3. **EMA超买超卖策略**：使用EMA来识别价格偏离均值的程度，当RSI低于设定的超卖阈值时产生买入信号，高于超买阈值时产生卖出信号。

4. **超级趋势策略**：基于ATR倍数设置价格通道，通过趋势变化来确定交易方向。当超级趋势指标由负转正时产生买入信号，由正转负时产生卖出信号。

5. **移动平均线交叉策略**：利用两条不同周期的移动平均线的交叉来确定市场趋势。当短期均线上穿长期均线时产生买入信号，下穿时产生卖出信号。

策略通过可自定义的权重系统对各个子策略的信号进行加权计算，只有当加权总和超过设定的阈值时才会触发交易。同时，策略还包含了潜在顶底识别机制，能够在市场可能反转时调整仓位。

这种多层次的信号确认机制有效减少了假信号，提高了交易系统的可靠性，同时灵活的参数设置使策略能够适应不同的交易品种和时间周期。

#### 策略优势
1. **信号多重确认**：通过五个独立的技术指标生成的信号进行加权计算，降低了单一指标可能带来的误导，提高了交易信号的质量和可靠性。

2. **自适应权重系统**：每个子策略可以分配不同的权重，使交易者能够根据自己对不同指标的信心度和历史表现调整策略的侧重点，提高了策略的灵活性。

3. **完善的风险管理**：策略内置了多层次的风险控制机制，包括止损、多级止盈和动态调整止损位的功能，确保在市场不利变动时能迅速控制风险。

4. **自动化潜在顶底识别**：通过综合分析RSI、交易量和价格走势，策略能够识别潜在的市场顶部和底部，并在适当时机部分平仓，锁定利润或减少损失。

5. **高度可定制性**：几乎所有参数都可以调整，包括各指标的计算周期、权重值、止盈止损百分比等，使交易者能够根据个人风格和不同市场条件优化策略。

6. **内置延迟机制**：为避免过早进入交易或基于噪音信号交易，策略采用了延迟确认机制，确保只有持续的信号才会触发交易，减少了短期波动的影响。

7. **时间过滤功能**：策略允许设置交易的起止日期，使交易者可以根据历史数据回测特定时间段的表现，或者避开已知的市场异常波动时期。

#### 策略风险
1. **参数过度优化风险**：由于参数众多，存在过度拟合历史数据的风险，可能导致策略在实盘交易中表现不佳。解决方法是在多个时间周期和品种上进行回测，采用相对稳健的参数设置，避免过度针对特定历史数据优化。

2. **市场条件变化风险**：策略在趋势市场和震荡市场的表现可能存在差异，市场状态的突然变化可能导致策略效果下降。解决方法是引入市场环境识别机制，在不同市场状态下调整参数或暂停交易。

3. **信号冲突风险**：多个指标同时使用可能产生相互矛盾的信号，导致决策混乱。解决方法是合理设置各指标的权重，强调更可靠的指标，并确保信号阈值设置合理以降低冲突概率。

4. **资金管理不当风险**：尽管策略包含止损机制，但不合理的资金管理仍可能导致资金快速耗尽。解决方法是严格控制每次交易的资金比例，确保单次交易的最大风险在可承受范围内。

5. **技术故障风险**：自动化交易系统可能面临网络中断、数据延迟等技术问题。解决方法是设置手动干预机制，定期监控系统运行状态，及时处理异常情况。

#### 策略优化方向
1. **加入市场环境过滤器**：开发一个能够识别当前市场是趋势性还是震荡性的指标，根据市场状态动态调整各子策略的权重，在趋势市场强化趋势跟踪策略，在震荡市场强化摆动策略。

2. **引入机器学习优化**：利用机器学习技术自动调整各指标的参数和权重，使策略能够根据最新的市场数据不断学习和适应，提高策略的动态适应能力。

3. **增加交易量分析**：将交易量变化作为额外的确认信号，只有在符合预期的交易量支持下才执行交易，提高信号的可信度。

4. **优化潜在顶底识别算法**：改进现有的顶底识别逻辑，加入更多的确认因素，如价格形态、多周期确认等，提高识别的准确性。

5. **加入情绪指标**：整合市场情绪指标，如恐慌指数（VIX）、看涨看跌期权比率等，在极端市场情绪时调整交易策略或暂停交易，避免在高波动期过度交易。

6. **开发动态止盈止损机制**：根据市场波动率自动调整止盈止损水平，在高波动市场拉宽止损范围，在低波动市场收紧止损，使风险管理更加灵活和有效。

7. **时间周期优化**：增加多时间周期分析功能，要求更高级别和更低级别的时间周期同时确认信号，减少假突破和假信号。

#### 总结
多指标加权智能交易策略通过整合多种技术分析工具并赋予不同权重，构建了一个全面且灵活的交易系统。该策略不仅具有信号多重确认、自适应权重系统和完善的风险管理功能，还包含了自动化的潜在顶底识别机制，使其在复杂多变的市场环境中展现出较强的适应能力。

尽管存在参数过度优化、市场条件变化和信号冲突等潜在风险，但通过合理的参数设置、市场环境识别和严格的资金管理，这些风险可以得到有效控制。未来的优化方向包括加入市场环境过滤器、引入机器学习技术、增强交易量分析和优化潜在顶底识别算法等，这些改进将进一步提升策略的稳定性和盈利能力。

对于寻求系统化交易方法的投资者而言，这种多指标加权智能交易策略提供了一个值得考虑的框架，它不仅能够降低情绪因素对交易决策的影响，还能通过数据驱动的方式持续优化交易表现。实施此策略时，建议从保守的参数设置开始，逐步调整并密切监控策略表现，以找到最适合个人风险偏好和市场条件的配置。
 || 
#### Overview
The Multi-Indicator Weighted Smart Trading Strategy is a comprehensive quantitative trading system that generates trading decisions by integrating signals from multiple technical indicators with different assigned weights. This strategy combines various technical analysis tools including MACD, Stochastic RSI, EMA, Supertrend, and moving average crossovers to form a comprehensive trading framework. The system not only supports multi-level take-profit and dynamic stop-loss mechanisms but also automatically adjusts trading parameters based on market conditions, maintaining high adaptability across different market environments. This strategy is particularly suitable for medium to long-term traders, using a weight allocation system to make trading decisions more robust and reliable.

#### Strategy Principle
The core of this strategy lies in its weighted signal system, which generates trading signals through five different sub-strategies:

1. **MACD Strategy**: Utilizes the crossover between the MACD line and the signal line to determine market trend direction. When the MACD line crosses above the signal line, it generates a buy signal; when it crosses below, it generates a sell signal.

2. **Stochastic RSI Strategy**: Combines the advantages of RSI and stochastic indicators to monitor market overbought and oversold conditions. Buy signals are generated when the Stochastic RSI falls below the set oversold threshold, and sell signals when it rises above the overbought threshold.

3. **EMA Overbought/Oversold Strategy**: Uses EMA to identify the degree of price deviation from the mean. Buy signals occur when RSI falls below the set oversold threshold, and sell signals when it rises above the overbought threshold.

4. **Supertrend Strategy**: Sets up a price channel based on ATR multiples and determines trading direction through trend changes. Buy signals are generated when the Supertrend indicator changes from negative to positive, and sell signals when it changes from positive to negative.

5. **Moving Average Crossover Strategy**: Uses the crossover of two moving averages with different periods to determine market trends. Buy signals occur when the short-term moving average crosses above the long-term moving average, and sell signals when it crosses below.

The strategy calculates weighted sums of signals from each sub-strategy using a customizable weight system, triggering trades only when the weighted sum exceeds a set threshold. Additionally, the strategy includes a potential top/bottom identification mechanism that adjusts positions when the market may reverse.

This multi-layered signal confirmation mechanism effectively reduces false signals, improving the reliability of the trading system, while flexible parameter settings allow the strategy to adapt to different trading instruments and time periods.

#### Strategy Advantages
1. **Multiple Signal Confirmation**: By calculating weighted signals generated from five independent technical indicators, the strategy reduces the potential misleading effects of single indicators, improving the quality and reliability of trading signals.

2. **Adaptive Weight System**: Each sub-strategy can be assigned different weights, allowing traders to adjust the strategy's focus based on their confidence in different indicators and historical performance, enhancing the strategy's flexibility.

3. **Comprehensive Risk Management**: The strategy incorporates multi-layered risk control mechanisms, including stop-loss, multi-level take-profit, and dynamic stop-loss adjustment functions, ensuring rapid risk control during adverse market movements.

4. **Automated Potential Top/Bottom Identification**: Through comprehensive analysis of RSI, trading volume, and price trends, the strategy can identify potential market tops and bottoms, partially closing positions at appropriate times to lock in profits or reduce losses.

5. **High Customizability**: Almost all parameters can be adjusted, including indicator calculation periods, weight values, take-profit and stop-loss percentages, allowing traders to optimize the strategy according to personal style and different market conditions.

6. **Built-in Delay Mechanism**: To avoid entering trades too early or based on noise signals, the strategy employs a delay confirmation mechanism, ensuring that only persistent signals trigger trades, reducing the impact of short-term fluctuations.

7. **Time Filtering Function**: The strategy allows setting start and end dates for trading, enabling traders to backtest performance for specific time periods based on historical data or avoid known periods of abnormal market volatility.

#### Strategy Risks
1. **Parameter Over-Optimization Risk**: With numerous parameters, there is a risk of overfitting historical data, potentially leading to poor performance in live trading. The solution is to backtest across multiple time periods and instruments, adopt relatively robust parameter settings, and avoid excessive optimization for specific historical data.

2. **Market Condition Change Risk**: The strategy's performance may vary between trending and ranging markets, and sudden changes in market state can lead to decreased effectiveness. The solution is to introduce a market environment recognition mechanism that adjusts parameters or pauses trading under different market conditions.

3. **Signal Conflict Risk**: Using multiple indicators simultaneously may produce contradictory signals, leading to confused decision-making. The solution is to set reasonable weights for each indicator, emphasize more reliable indicators, and ensure appropriate signal threshold settings to reduce conflict probability.

4. **Improper Fund Management Risk**: Despite the strategy's stop-loss mechanisms, unreasonable fund management can still lead to rapid depletion of capital. The solution is to strictly control the proportion of funds for each trade, ensuring that the maximum risk per trade is within an acceptable range.

5. **Technical Failure Risk**: Automated trading systems may face technical issues such as network interruptions and data delays. The solution is to set up manual intervention mechanisms, regularly monitor system operation status, and promptly address abnormal situations.

#### Strategy Optimization Directions
1. **Incorporate Market Environment Filter**: Develop an indicator that can identify whether the current market is trending or ranging, dynamically adjusting the weights of each sub-strategy based on market state, strengthening trend-following strategies in trending markets and oscillating strategies in ranging markets.

2. **Introduce Machine Learning Optimization**: Utilize machine learning techniques to automatically adjust parameters and weights of various indicators, enabling the strategy to continuously learn and adapt based on the latest market data, improving its dynamic adaptation capability.

3. **Add Volume Analysis**: Use volume changes as additional confirmation signals, executing trades only when supported by expected volume, increasing the credibility of signals.

4. **Optimize Potential Top/Bottom Identification Algorithm**: Improve the existing top/bottom identification logic by adding more confirmation factors, such as price patterns and multi-period confirmation, enhancing identification accuracy.

5. **Add Sentiment Indicators**: Integrate market sentiment indicators, such as the VIX (fear index) and the call-put ratio, to adjust trading strategies or pause trading during extreme market sentiment, avoiding excessive trading during high volatility periods.

6. **Develop Dynamic Take-Profit and Stop-Loss Mechanisms**: Automatically adjust take-profit and stop-loss levels based on market volatility, widening stop-loss ranges in high-volatility markets and tightening them in low-volatility markets, making risk management more flexible and effective.

7. **Time Period Optimization**: Add multi-timeframe analysis functionality, requiring signal confirmation from both higher and lower timeframes simultaneously, reducing false breakouts and false signals.

#### Summary
The Multi-Indicator Weighted Smart Trading Strategy constructs a comprehensive and flexible trading system by integrating various technical analysis tools with different weights. This strategy not only features multiple signal confirmation, an adaptive weight system, and comprehensive risk management functions but also includes an automated potential top/bottom identification mechanism, demonstrating strong adaptability in complex and changing market environments.

Although there are potential risks such as parameter over-optimization, market condition changes, and signal conflicts, these risks can be effectively controlled through reasonable parameter settings, market environment recognition, and strict fund management. Future optimization directions include incorporating market environment filters, introducing machine learning techniques, enhancing volume analysis, and optimizing potential top/bottom identification algorithms. These improvements will further enhance the strategy's stability and profitability.

For investors seeking systematic trading methods, this multi-indicator weighted smart trading strategy provides a framework worth considering. It not only reduces the impact of emotional factors on trading decisions but also continuously optimizes trading performance through a data-driven approach. When implementing this strategy, it is recommended to start with conservative parameter settings, gradually adjust and closely monitor strategy performance to find the configuration that best suits personal risk preferences and market conditions.
[/trans]



> Source (PineScript)

``` pinescript
/*backtest
start: 2024-09-08 00:00:00
end: 2025-02-23 08:00:00
period: 2d
basePeriod: 2d
exchanges: [{"eid":"Binance","currency":"ETH_USDT"}]
*/

// **********************************************************************************************************************************************************************************************************************************************************************
// Last update: 08/03/2022
// *************************************************************************************************************************************************************************************************************************************************************************
//@version=5
strategy(title='Smart trading', overlay=true, precision=2, commission_value=0.075, commission_type=strategy.commission.percent, initial_capital=1000, currency=currency.USD, default_qty_type=strategy.percent_of_equity, default_qty_value=100, slippage=1,calc_on_every_tick = false,calc_on_order_fills = true)
// *************************************************************************************************************************************************************************************************************************************************************************
// COMMENTS
// *************************************************************************************************************************************************************************************************************************************************************************
chat_id = input("-1001587924564",'Chat ID Telegram')
procent_stop = input.float(1.0,'Процент стоп')
procent_teik = input.float(4.0,'Процент TP4 ')

// *************************************************************************************************************************************************************************************************************************************************************************
// INPUTS
// *************************************************************************************************************************************************************************************************************************************************************************
// * Type trading
allow_longs = input.bool(true, 'Только лонги', group='Trading type')
allow_shorts = input.bool(true, 'Только шорты', group='Trading type')
// * Datastamp
from_day = input.int(1, 'From Day', minval=1, maxval=31, group='DataStamp')
from_month = input.int(1, 'From Month', minval=1, maxval=12, group='DataStamp')
from_year = input.int(2021, 'From Year', minval=1980, maxval=9999, group='DataStamp')
to_day = input.int(1, 'To Day', minval=1, maxval=31, group='DataStamp')
to_month = input.int(1, 'To Month', minval=1, maxval=12, group='DataStamp')
to_year = input.int(9999, 'To Year', minval=2017, maxval=9999, group='DataStamp')
// * Stop loss
stoploss = input.bool(true, 'Стоп лосс в стратегии', group='Stop loss')
movestoploss = input.string('TP-2', 'Перенос стопа', options=['None', 'Percentage', 'TP-1', 'TP-2', 'TP-3'], group='Stop loss')
movestoploss_entry = input.bool(false, 'Перенос стопа на твх', group='Stop loss')
stoploss_perc = input.float(6.0, 'Стоп лосс в %', minval=0, maxval=100, group='Stop loss') * 0.01
move_stoploss_factor = input.float(20.0, 'Фактор переноса стопа в %', group='Stop loss') * 0.01 + 1
stop_source = input.source(hl2, 'Stop Source', group='Stop loss')
// * Take profits
take_profits = input.bool(true, 'Тейк профит в стратегии', group='Take Profits')
// retrade= input.bool(false, 'Retrade', group='Take Profits')
MAX_TP = input.int(6, 'Кол-во TP', minval=1, maxval=10, group='Take Profits')
long_profit_perc = input.float(6.8, 'Long - TP в % каждый', minval=0.0, maxval=999, step=1, group='Take Profits') * 0.01
long_profit_qty = input.float(15, 'Long - TP в % от твх', minval=0.0, maxval=100, step=1, group='Take Profits')
short_profit_perc = input.float(13, 'Short - TP в % каждый', minval=0.0, maxval=999, step=1, group='Take Profits') * 0.01
short_profit_qty = input.float(10, 'Short - TP в % от твх', minval=0.0, maxval=100, step=1, group='Take Profits')
// * Delays
delay_macd = input.int(1, 'Candles delay MACD', minval=1, group='Delays')
delay_srsi = input.int(2, 'Candles delay RSI', minval=1, group='Delays')
delay_rsi = input.int(2, 'Candles delay EMA', minval=1, group='Delays')
delay_super = input.int(1, 'Candles delay Supertrend', minval=1, group='Delays')
delay_cross = input.int(1, 'Candles delay MA', minval=1, group='Delays')
delay_exit = input.int(7, 'Candles delay exit', minval=1, group='Delays')
// * Inputs Smart strategies
str_0 = input.bool(true, 'Strategy 0: Weighted Strategy', group='Weights')
weight_trigger = input.int(2, 'Smart Signal entry [0, 5]', minval=0, maxval=5, step=1, group='Weights')
weight_str1 = input.int(1, 'Smart Strategy 1 [0, 5]', minval=0, maxval=5, step=1, group='Weights')
weight_str2 = input.int(1, 'Smart Strategy 2 [0, 5]', minval=0, maxval=5, step=1, group='Weights')
weight_str3 = input.int(1, 'Smart Strategy 3 [0, 5]', minval=0, maxval=5, step=1, group='Weights')
weight_str4 = input.int(1, 'Smart Strategy 4 [0, 5]', minval=0, maxval=5, step=1, group='Weights')
weight_str5 = input.int(1, 'Smart Strategy 5 [0, 5]', minval=0, maxval=5, step=1, group='Weights')
// * Inputs strategy 1: MACD 
str_1 = input.bool(true, 'Strategy 1: MACD', group='Strategy 1: MACD')
MA1_period_1 = input.int(16, 'MA 1', minval=1, maxval=9999, step=1, group='Strategy 1: MACD')
MA1_type_1 = input.string('EMA', 'MA1 Type', options=['RMA', 'SMA', 'EMA', 'WMA', 'HMA', 'DEMA', 'TEMA', 'VWMA'], group='Strategy 1: MACD')
MA1_source_1 = input.source(hl2, 'MA1 Source', group='Strategy 1: MACD')
MA2_period_1 = input.int(36, 'MA 2', minval=1, maxval=9999, step=1, group='Strategy 1: MACD')
MA2_type_1 = input.string('EMA', 'MA2 Type', options=['RMA', 'SMA', 'EMA', 'WMA', 'HMA', 'DEMA', 'TEMA', 'VWMA'], group='Strategy 1: MACD')
MA2_source_1 = input.source(high, 'MA2 Source', group='Strategy 1: MACD')
// * Inputs strategy 2: RSI oversold/overbought
str_2 = input.bool(true, 'Strategy 2: RSI', group='Strategy 2: RSI')
long_RSI = input.float(70, 'Exit RSI Long (%)', minval=0.0, step=1, group='Strategy 2: RSI')
short_RSI = input.float(27, 'Exit RSI Short (%)', minval=0.0, step=1, group='Strategy 2: RSI')
length_RSI = input.int(14, 'RSI Length', group='Strategy 2: RSI')
length_stoch = input.int(14, 'RSI Stochastic', group='Strategy 2: RSI')
smoothK = input.int(3, 'Smooth', group='Strategy 2: RSI')
// * Inputs strategy 3: EMA oversold/overbought
str_3 = input.bool(true, 'Strategy 3: RSI', group='Strategy 3: RSI')
long_RSI2 = input.float(77, 'Exit EMA Long', minval=0.0, step=1, group='Strategy 3: RSI')
short_RSI2 = input.float(30, 'Exit EMA Short', minval=0.0, step=1, group='Strategy 3: RSI')
// * Inputs strategy 4: Supertrend
str_4 = input.bool(true, 'Strategy 4: Supertrend', group='Strategy 4: Supertrend')
periods_4 = input.int(2, 'ATR Period', group='Strategy 4: Supertrend')
source_4 = input.source(hl2, 'Source', group='Strategy 4: Supertrend')
multiplier = input.float(2.4, 'ATR Multiplier', step=0.1, group='Strategy 4: Supertrend')
change_ATR = input.bool(true, 'Change ATR Calculation Method ?', group='Strategy 4: Supertrend')
// * Inputs strategy 5: MA
str_5 = input.bool(true, 'Strategy 5: MA', group='Strategy 5: MA')
MA1_period_5 = input.int(46, 'MA 1', minval=1, maxval=9999, step=1, group='Strategy 5: MA')
MA1_type_5 = input.string('EMA', 'MA1 Type', options=['RMA', 'SMA', 'EMA', 'WMA', 'HMA', 'DEMA', 'TEMA', 'VWMA'], group='Strategy 5: MA')
MA1_source_5 = input.source(close, 'MA1 Source', group='Strategy 5: MA')
MA2_period_5 = input.int(82, 'MA 2', minval=1, maxval=9999, step=1, group='Strategy 5: MA')
MA2_type_5 = input.string('EMA', 'MA2 Type', options=['RMA', 'SMA', 'EMA', 'WMA', 'HMA', 'DEMA', 'TEMA', 'VWMA'], group='Strategy 5: MA')
MA2_source_5 = input.source(close, 'MA2 Source', group='Strategy 5: MA')
// * Inputs Potential TOP/BOTTOM
str_6 = input.bool(false, 'Потенциальные ордера long/short', group='Potential TOP/BOTTOM')
top_qty = input.float(30, 'Лонг закрыть (%) из оставшейся позиции', minval=0.0, maxval=100, step=1, group='Potential TOP/BOTTOM')
bottom_qty = input.float(30, 'Шорт закрыть (%) из оставшейся позиции', minval=0.0, maxval=100, step=1, group='Potential TOP/BOTTOM') 
source_6_top = input.source(close, 'TP-TOP на предыдущий', group='Potential TOP/BOTTOM')
source_6_bottom = input.source(close, 'TP-BOTTOM на предыдущий', group='Potential TOP/BOTTOM')
long_trail_perc = input.float(150, 'Объем Long (%)', minval=0.0, step=1, group='Potential TOP/BOTTOM') * 0.01
short_trail_perc = input.float(150, 'Объем Short (%)', minval=0.0, step=1, group='Potential TOP/BOTTOM') * 0.01
// * Flags
FLAG_SIGNALS = input.bool(true, 'Show Buy/Sell Signals ?', group='Miscellaneous')
FLAG_SHADOWS = input.bool(true, 'Show shadows satisfied strategies ?', group='Miscellaneous')
// * Alarms
alarm_label_long = input.string('Buy', 'Label open long', group='Basic alarm system')
alarm_label_short = input.string('Sell', 'Label open short', group='Basic alarm system')
alarm_label_close_long = input.string('Close long', 'Label close long', group='Basic alarm system')
alarm_label_close_short = input.string('Close short', 'Label close short', group='Basic alarm system')
alarm_label_TP_long = input.string('TP long', 'Label Take Profit long', group='Basic alarm system')
alarm_label_TP_short = input.string('TP short', 'Label Take Profit short', group='Basic alarm system')
alarm_label_SL = input.string('SL', 'Label Stop-Loss', group='Basic alarm system')
// *************************************************************************************************************************************************************************************************************************************************************************
// ABBREVIATIONS
// *************************************************************************************************************************************************************************************************************************************************************************
// TP: Take profits
// SL: Stop-Loss
// *************************************************************************************************************************************************************************************************************************************************************************
// GLOBAL VARIABLES
// *************************************************************************************************************************************************************************************************************************************************************************
start = timestamp(from_year, from_month, from_day, 00, 00) // backtest start window
end = timestamp(to_year, to_month, to_day, 23, 59)// backtest finish window
var FLAG_FIRST = false
var price_stop_long = 0.
var price_stop_short = 0.
var profit_qty = 0. // Quantity to close per TP from open position
var profit_perc = 0. // Percentage to take profits since open position or last TP
var nextTP = 0. // Next target to take profits
var since_entry = 0 // Number of bars since open last postion
var since_close = 0 // Number of bars since close or TP/STOP last position

// * Compute profit quantity and profit percentage
if strategy.position_size > 0
    profit_qty := long_profit_qty
    profit_perc := long_profit_perc
else if strategy.position_size < 0
    profit_qty := short_profit_qty
    profit_perc := short_profit_perc
else
    nextTP := 0. // Next Take Profit target (out of market)
// *************************************************************************************************************************************************************************************************************************************************************************
// FUNCTIONS
// *************************************************************************************************************************************************************************************************************************************************************************
// * MA type
// *************************************************************************************************************************************************************************************************************************************************************************
ma(MAType, MASource, MAPeriod) =>
    if MAType == 'SMA'
        ta.sma(MASource, MAPeriod)
    else if MAType == 'EMA'
        ta.ema(MASource, MAPeriod)
    else if MAType == 'WMA'
        ta.wma(MASource, MAPeriod)
    else if MAType == 'RMA'
        ta.rma(MASource, MAPeriod)
    else if MAType == 'HMA'
        ta.wma(2 * ta.wma(MASource, MAPeriod / 2) - ta.wma(MASource, MAPeriod), math.round(math.sqrt(MAPeriod)))
    else if MAType == 'DEMA'
        e = ta.ema(MASource, MAPeriod)
        2 * e - ta.ema(e, MAPeriod)
    else if MAType == 'TEMA'
        e = ta.ema(MASource, MAPeriod)
        3 * (e - ta.ema(e, MAPeriod)) + ta.ema(ta.ema(e, MAPeriod), MAPeriod)
    else if MAType == 'VWMA'
        ta.vwma(MASource, MAPeriod)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Number strategies
// *************************************************************************************************************************************************************************************************************************************************************************
n_strategies() =>
    var result = 0.
    if str_1
        result := 1.
    if str_2
        result += 1.
    if str_3
        result += 1.
    if str_4
        result += 1.
    if str_5
        result += 1.
// *************************************************************************************************************************************************************************************************************************************************************************
// * Price take profit
// *************************************************************************************************************************************************************************************************************************************************************************
price_takeProfit(percentage, N) =>
    if strategy.position_size > 0
        strategy.position_avg_price * (1 + N * percentage)
    else
        strategy.position_avg_price * (1 - N * percentage)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Weigthed values
// *************************************************************************************************************************************************************************************************************************************************************************
weight_values(signal) =>
    if signal
        weight = 1.0
    else
        weight = 0.
// *************************************************************************************************************************************************************************************************************************************************************************
// * Weigthed total
// *************************************************************************************************************************************************************************************************************************************************************************
weight_total(signal1, signal2, signal3, signal4, signal5) =>
    weight_str1 * weight_values(signal1) + weight_str2 * weight_values(signal2) + weight_str3 * weight_values(signal3) + weight_str4 * weight_values(signal4) + weight_str5 * weight_values(signal5)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Set alert TP message
// *************************************************************************************************************************************************************************************************************************************************************************
set_alarm_label_TP() =>
    if strategy.position_size > 0
        alarm_label_TP_long
    else if strategy.position_size < 0
        alarm_label_TP_short 
// *************************************************************************************************************************************************************************************************************************************************************************
// * Color
// *************************************************************************************************************************************************************************************************************************************************************************
colors(type, value=0) =>
    switch str.lower(type)
        'buy'=> color.new(color.aqua, value)
        'sell' => color.new(color.gray, value)
        'TP' => color.new(color.aqua, value)
        'SL' => color.new(color.gray, value)
        'signal' => color.new(color.orange, value)
        'profit' => color.new(color.teal, value)
        'loss' => color.new(color.red, value)
        'info' => color.new(color.white, value)
        'highlights' => color.new(color.orange, value)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Bar since last entry
// *************************************************************************************************************************************************************************************************************************************************************************
bars_since_entry() =>
    bar_index - strategy.opentrades.entry_bar_index(0)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Bar since close or TP/STOP
// *************************************************************************************************************************************************************************************************************************************************************************
bars_since_close() =>
    ta.barssince(ta.change(strategy.closedtrades))
// *************************************************************************************************************************************************************************************************************************************************************************
// ADDITIONAL GLOBAL VARIABLES
// *************************************************************************************************************************************************************************************************************************************************************************
// * Compute time since last entry and last close/TP position
since_entry := bars_since_entry()
since_close := bars_since_close()
if strategy.opentrades == 0
    since_entry := delay_exit
if strategy.closedtrades == 0
    since_close := delay_exit
// *************************************************************************************************************************************************************************************************************************************************************************
// STRATEGIES
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 1: MACD
// *************************************************************************************************************************************************************************************************************************************************************************
MA1 = ma(MA1_type_1, MA1_source_1, MA1_period_1)
MA2 = ma(MA2_type_1, MA2_source_1, MA2_period_1)

MACD = MA1 - MA2
signal = ma('SMA', MACD, 9)
trend= MACD - signal

long = MACD > signal
short = MACD < signal
proportion = math.abs(MACD / signal)

// * Conditions
long_signal1 = long and long[delay_macd - 1] and not long[delay_macd]
short_signal1 = short and short[delay_macd - 1] and not short[delay_macd]
close_long1 = short and not long[delay_macd]
close_short1 = long and not short[delay_macd]
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 2: STOCH RSI
// *************************************************************************************************************************************************************************************************************************************************************************
rsi = ta.rsi(close, length_RSI)
srsi = ta.stoch(rsi, rsi, rsi, length_stoch)
k = ma('SMA', srsi, smoothK)
isRsiOB = k >= long_RSI
isRsiOS = k <= short_RSI

// * Conditions
long_signal2 = isRsiOS[delay_srsi] and not isRsiOB and since_entry >= delay_exit and since_close >= delay_exit
short_signal2 = isRsiOB[delay_srsi] and not isRsiOS and since_entry >= delay_exit and since_close >= delay_exit
close_long2 = short_signal2
close_short2 = long_signal2
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 3: RSI
// *************************************************************************************************************************************************************************************************************************************************************************
isRsiOB2 = rsi >= long_RSI2
isRsiOS2 = rsi <= short_RSI2

// * Conditions
long_signal3 = isRsiOS2[delay_rsi] and not isRsiOB2 and since_entry >= delay_exit and since_close >= delay_exit
short_signal3 = isRsiOB2[delay_rsi] and not isRsiOS2 and since_entry >= delay_exit and since_close >= delay_exit
close_long3 = short_signal3
close_short3 = long_signal3
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 4: SUPERTREND
// *************************************************************************************************************************************************************************************************************************************************************************
atr2 = ma('SMA', ta.tr, periods_4)
atr = change_ATR ? ta.atr(periods_4) : atr2
up = source_4 - multiplier * atr
up1 = nz(up[1], up)
up := close[1] > up1 ? math.max(up, up1) : up

dn = source_4 + multiplier * atr
dn1 = nz(dn[1], dn)
dn := close[1] < dn1 ? math.min(dn, dn1) : dn

trend := 1
trend := nz(trend[1], trend)
trend := trend == -1 and close > dn1 ? 1 : trend == 1 and close < up1 ? -1 : trend

// * Conditions
long4 = trend == 1
short4 = trend == -1
long_signal4 = trend == 1 and trend[delay_super - 1] == 1 and trend[delay_super] == -1
short_signal4 = trend == -1 and trend[delay_super - 1] == -1 and trend[delay_super] == 1
changeCond = trend != trend[1]
close_long4 = short_signal4
close_short4 = short_signal4
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 5: MA CROSS
// *************************************************************************************************************************************************************************************************************************************************************************
MA12 = ma(MA1_type_5, MA1_source_5, MA1_period_5)
MA22 = ma(MA2_type_5, MA2_source_5, MA2_period_5)

long5 = MA12 > MA22
short5 = MA12 < MA22

// * Conditions
long_signal5 = long5 and long5[delay_cross - 1] and not long5[delay_cross]
short_signal5 = short5 and short5[delay_cross - 1] and not short5[delay_cross]
close_long5 = short5 and not long5[delay_cross]
close_short5 = long5 and not short5[delay_cross]
// *************************************************************************************************************************************************************************************************************************************************************************
// * STRATEGY 6: POTENTIAL TOP/BOTTOM
// *************************************************************************************************************************************************************************************************************************************************************************
// * Combination RSI, Stoch RSI, MACD, volume, and weighted-strategy to detect potential TOP/BOTTOMS areas
volumeRSI_condition = volume[2] > volume[3] and volume[2] > volume[4] and volume[2] > volume[5]
condition_OB1 = isRsiOB2 and (isRsiOB or volume < ma('SMA', volume, 20) / 2) and volumeRSI_condition
condition_OS1 = isRsiOS2 and (isRsiOS or volume < ma('SMA', volume, 20) / 2) and volumeRSI_condition

condition_OB2 = volume[2] / volume[1] > (1.0 + long_trail_perc) and isRsiOB and volumeRSI_condition
condition_OS2 = volume[2] / volume[1] > (1.0 + short_trail_perc) and isRsiOS and volumeRSI_condition

condition_OB3 = weight_total(MACD < signal, isRsiOB, isRsiOB2, short4, short5) >= weight_trigger
condition_OS3 = weight_total(MACD > signal, isRsiOS, isRsiOS2, long4, long5) >= weight_trigger

condition_OB = (condition_OB1 or condition_OB2)
condition_OS = (condition_OS1 or condition_OS2)
condition_OB_several = condition_OB[1] and condition_OB[2] or condition_OB[1] and condition_OB[3] or condition_OB[1] and condition_OB[4] or condition_OB[1] and condition_OB[5] or condition_OB[1] and condition_OB[6] or condition_OB[1] and condition_OB[7] 
condition_OS_several = condition_OS[1] and condition_OS[2] or condition_OS[1] and condition_OS[3] or condition_OS[1] and condition_OS[4] or condition_OS[1] and condition_OS[5] or condition_OS[1] and condition_OS[6] or condition_OS[1] and condition_OS[7] 
// *************************************************************************************************************************************************************************************************************************************************************************
// STRATEGY ENTRIES AND EXITS
// *************************************************************************************************************************************************************************************************************************************************************************


long_SL = close - ((close / 100) * procent_stop)
long_OP = close
long_TP_1 = close + ((close / 100) * (procent_teik * 1.1))
long_TP_2 = close + ((close / 100) * (procent_teik * 1.8))
long_TP_3 = close + ((close / 100) * (procent_teik * 2.8))
long_TP_4 = close + ((close / 100) * (procent_teik * 4.5))

short_SL = close + ((close / 100) * procent_stop)
short_OP = close
short_TP_1 = close - ((close / 100) * (procent_teik * 1.1))
short_TP_2 = close - ((close / 100) * (procent_teik * 1.8))
short_TP_3 = close - ((close / 100) * (procent_teik * 2.8))
short_TP_4 = close - ((close / 100) * (procent_teik * 4.5))


if time >= start and time <= end
    // ***************************************************************************************************************************************************************************
    // * Set Entries
    // ***************************************************************************************************************************************************************************
    if str_0
        if not str_1
            weight_str1 := 0
        if not str_2
            weight_str2 := 0
        if not str_3
            weight_str3 := 0
        if not str_4
            weight_str4 := 0
        if not str_5
            weight_str5 := 0
        if allow_shorts == true
            w_total = weight_total(short_signal1, short_signal2, short_signal3, short_signal4, short_signal5)
            if w_total >= weight_trigger
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')
                


                strategy.entry('Short', strategy.short)
        if allow_longs == true
            w_total = weight_total(long_signal1, long_signal2, long_signal3, long_signal4, long_signal5)
            if w_total >= weight_trigger
                strategy.entry('Long', strategy.long)
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

    else
        if allow_shorts == true
            if str_1
                strategy.entry('Short', strategy.short, when=short_signal1)
                // alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT')  + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL))  + str.tostring(math.round_to_mintick(close)) + '"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_2
                strategy.entry('Short', strategy.short, when=short_signal2)
                // alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT')  + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL))  + str.tostring(math.round_to_mintick(close)) + '"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_3
                strategy.entry('Short', strategy.short, when=short_signal3)
                // alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT')  + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL))  + str.tostring(math.round_to_mintick(close)) + '"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_4
                strategy.entry('Short', strategy.short, when=short_signal4)
                // alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT')  + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL))  + str.tostring(math.round_to_mintick(close)) + '"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_5
                strategy.entry('Short', strategy.short, when=short_signal5)
                // alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL))  + str.tostring(math.round_to_mintick(close)) + '"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('SHORT') + ' ' + str.tostring(math.round_to_mintick(short_TP_1)) + ' ' + str.tostring(math.round_to_mintick(short_TP_2)) + ' ' + str.tostring(math.round_to_mintick(short_TP_3)) + ' ' + str.tostring(math.round_to_mintick(short_TP_4)) + ' ' + str.tostring(math.round_to_mintick(short_SL)) + ' ' + str.tostring(math.round_to_mintick(close)) + '"}')

        if allow_longs == true
            if str_1
                strategy.entry('Long', strategy.long, when=long_signal1)
                // alert('{"chat_id":"'+ chat_id +'","text":"#' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' min'+ '\n' + str.tostring('LONG') + '\n' +'Вход на 1-3% от депозита \n' + 'TP 1: ' + str.tostring(math.round_to_mintick(long_TP_1)) + '\n' + 'TP 2: ' + str.tostring(math.round_to_mintick(long_TP_2)) + '\n' + 'TP 3: ' + str.tostring(math.round_to_mintick(long_TP_3)) + '\n' + 'TP 4: ' + str.tostring(math.round_to_mintick(long_TP_4)) + '\n' + '?? STOP: ' + str.tostring(math.round_to_mintick(long_SL))  +'"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_2
                strategy.entry('Long', strategy.long, when=long_signal2)
                // alert('{"chat_id":"'+ chat_id +'","text":"#' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' min'+ '\n' + str.tostring('LONG') + '\n' +'Вход на 1-3% от депозита \n' + 'TP 1: ' + str.tostring(math.round_to_mintick(long_TP_1)) + '\n' + 'TP 2: ' + str.tostring(math.round_to_mintick(long_TP_2)) + '\n' + 'TP 3: ' + str.tostring(math.round_to_mintick(long_TP_3)) + '\n' + 'TP 4: ' + str.tostring(math.round_to_mintick(long_TP_4)) + '\n' + '?? STOP: ' + str.tostring(math.round_to_mintick(long_SL))  +'"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_3
                strategy.entry('Long', strategy.long, when=long_signal3)
                // alert('{"chat_id":"'+ chat_id +'","text":"#' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' min'+ '\n' + str.tostring('LONG') + '\n' +'Вход на 1-3% от депозита \n' + 'TP 1: ' + str.tostring(math.round_to_mintick(long_TP_1)) + '\n' + 'TP 2: ' + str.tostring(math.round_to_mintick(long_TP_2)) + '\n' + 'TP 3: ' + str.tostring(math.round_to_mintick(long_TP_3)) + '\n' + 'TP 4: ' + str.tostring(math.round_to_mintick(long_TP_4)) + '\n' + '?? STOP: ' + str.tostring(math.round_to_mintick(long_SL))  +'"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_4
                strategy.entry('Long', strategy.long, when=long_signal4)
                // alert('{"chat_id":"'+ chat_id +'","text":"#' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' min'+ '\n' + str.tostring('LONG') + '\n' +'Вход на 1-3% от депозита \n' + 'TP 1: ' + str.tostring(math.round_to_mintick(long_TP_1)) + '\n' + 'TP 2: ' + str.tostring(math.round_to_mintick(long_TP_2)) + '\n' + 'TP 3: ' + str.tostring(math.round_to_mintick(long_TP_3)) + '\n' + 'TP 4: ' + str.tostring(math.round_to_mintick(long_TP_4)) + '\n' + '?? STOP: ' + str.tostring(math.round_to_mintick(long_SL))  +'"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

            if str_5
                strategy.entry('Long', strategy.long, when=long_signal5)
                // alert('{"chat_id":"'+ chat_id +'","text":"#' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' min'+ '\n' + str.tostring('LONG') + '\n' +'Вход на 1-3% от депозита \n' + 'TP 1: ' + str.tostring(math.round_to_mintick(long_TP_1)) + '\n' + 'TP 2: ' + str.tostring(math.round_to_mintick(long_TP_2)) + '\n' + 'TP 3: ' + str.tostring(math.round_to_mintick(long_TP_3)) + '\n' + 'TP 4: ' + str.tostring(math.round_to_mintick(long_TP_4)) + '\n' + '?? STOP: ' + str.tostring(math.round_to_mintick(long_SL))  +'"}')
                alert('{"chat_id":"'+ chat_id +'","text":"' + syminfo.ticker + ' ' + str.tostring(timeframe.period) + ' ' + str.tostring('LONG') + ' ' + str.tostring(math.round_to_mintick(long_TP_1)) + ' ' + str.tostring(math.round_to_mintick(long_TP_2)) + ' ' + str.tostring(math.round_to_mintick(long_TP_3)) + ' ' + str.tostring(math.round_to_mintick(long_TP_4)) + ' ' + str.tostring(math.round_to_mintick(long_SL)) + ' '  + str.tostring(math.round_to_mintick(close)) + '"}')

    // ***************************************************************************************************************************************************************************
    // * Set Take Profits
    // ***************************************************************************************************************************************************************************
    if strategy.position_size != 0 and take_profits and since_entry == 0
        for i = 1 to MAX_TP
            id = 'TP ' + str.tostring(i)
            strategy.exit(id=id, limit=price_takeProfit(profit_perc, i), qty_percent=profit_qty, comment=id)
    // ***************************************************************************************************************************************************************************
    // * Set Stop loss
    // ***************************************************************************************************************************************************************************
    if strategy.position_size > 0
        if since_close == 0
            if high > price_takeProfit(profit_perc, 6) and MAX_TP >= 6
                n = 6
                nextTP := na
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_long := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_long := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_long := price_takeProfit(profit_perc, n-3)
            else if high > price_takeProfit(profit_perc, 5) and MAX_TP >= 5
                n = 5
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_long := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_long := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_long := price_takeProfit(profit_perc, n-3)
            else if high > price_takeProfit(profit_perc, 4) and MAX_TP >= 4
                n = 4
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_long := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_long := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_long := price_takeProfit(profit_perc, n-3)
            else if high > price_takeProfit(profit_perc, 3) and MAX_TP >= 3
                n = 3
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_long := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_long := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
            else if high > price_takeProfit(profit_perc, 2) and MAX_TP >= 2
                n = 2
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_long := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
            else if high > price_takeProfit(profit_perc, 1) and MAX_TP >= 1
                n = 1
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_long := strategy.position_avg_price * (1 + n*profit_perc - stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
                else if movestoploss == 'TP-2' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_long := strategy.position_avg_price
        if since_entry == 0
            n = 0
            nextTP := price_takeProfit(profit_perc, n + 1)
            price_stop_long := strategy.position_avg_price * (1 - stoploss_perc) 
    if strategy.position_size < 0
        if since_close == 0
            if low < price_takeProfit(profit_perc, 6) and MAX_TP >= 6
                n = 6
                nextTP := na
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_short := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_short := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_short := price_takeProfit(profit_perc, n-3)
            else if low < price_takeProfit(profit_perc, 5) and MAX_TP >= 5
                n = 5
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_short := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_short := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_short := price_takeProfit(profit_perc, n-3)
            else if low < price_takeProfit(profit_perc, 4) and MAX_TP >= 4
                n = 4
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_short := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_short := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3'
                    price_stop_short := price_takeProfit(profit_perc, n-3)
            else if low < price_takeProfit(profit_perc, 3) and MAX_TP >= 3
                n = 3
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_short := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2'
                    price_stop_short := price_takeProfit(profit_perc, n-2)
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
            else if low < price_takeProfit(profit_perc, 2) and MAX_TP >= 2
                n = 2
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1'
                    price_stop_short := price_takeProfit(profit_perc, n-1)
                else if movestoploss == 'TP-2' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
            else if low < price_takeProfit(profit_perc, 1) and MAX_TP >= 1
                n = 1 
                nextTP := price_takeProfit(profit_perc, n + 1)
                if movestoploss == 'Percentage'
                    price_stop_short := strategy.position_avg_price * (1 - n*profit_perc + stoploss_perc * move_stoploss_factor)
                else if movestoploss == 'TP-1' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
                else if movestoploss == 'TP-2' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
                else if movestoploss == 'TP-3' and movestoploss_entry
                    price_stop_short := strategy.position_avg_price
        if since_entry == 0
            n = 0
            nextTP := price_takeProfit(profit_perc, n + 1)
            price_stop_short := strategy.position_avg_price * (1 + stoploss_perc)
    // ***************************************************************************************************************************************************************************
    // * Set Exits
    // ***************************************************************************************************************************************************************************
    if allow_longs == true and allow_shorts == false
        if str_0
            w_total = weight_total(short_signal1, short_signal2, short_signal3, short_signal4, short_signal5)
            strategy.close('Long', when=w_total>=weight_trigger, qty_percent=100, comment='SHORT')
        else
            if str_1
                strategy.close('Long', when=close_long1, qty_percent=100, comment='SHORT')
            if str_2
                strategy.close('Long', when=close_long2, qty_percent=100, comment='SHORT')
            if str_3
                strategy.close('Long', when=close_long3, qty_percent=100, comment='SHORT')
            if str_4
                strategy.close('Long', when=close_long4, qty_percent=100, comment='SHORT')
            if str_5
                strategy.close('Long', when=close_long5, qty_percent=100, comment='SHORT')
    if allow_longs == false and allow_shorts == true
        if str_0
            w_total = weight_total(long_signal1, long_signal2, long_signal3, long_signal4, long_signal5)
            strategy.close('Short', when=w_total>=weight_trigger, qty_percent=100, comment='LONG')
        else
            if str_1
                strategy.close('Short', when=close_long1, qty_percent=100, comment='LONG')
            if str_2
                strategy.close('Short', when=close_long2, qty_percent=100, comment='LONG')
            if str_3
                strategy.close('Short', when=close_long3, qty_percent=100, comment='LONG')
            if str_4
                strategy.close('Short', when=close_long4, qty_percent=100, comment='LONG')
            if str_5
                strategy.close('Short', when=close_long5, qty_percent=100, comment='LONG')
    if allow_shorts == true and strategy.position_size < 0 and stoploss and since_entry > 0
        strategy.close('Short', when=stop_source >= price_stop_short, qty_percent=100, comment='STOP')
        if str_6
            if top_qty == 100
                strategy.close('Short', when=condition_OS_several, qty_percent=bottom_qty, comment='STOP')
            else    
                strategy.exit('Short', when=condition_OS_several, limit=source_6_bottom[1], qty_percent=bottom_qty, comment='TP-B')
    if allow_longs == true and strategy.position_size > 0 and stoploss and since_entry > 0
        strategy.close('Long', when=stop_source <= price_stop_long, qty_percent=100, comment='STOP')
        if str_6
            if top_qty == 100
                strategy.close('Long', when=condition_OB_several, qty_percent=top_qty, comment='STOP')
            else
                strategy.exit('Long', when=condition_OB_several, limit=source_6_top[1], qty_percent=top_qty, comment='TP-T')
// ***********************************************************************************************************************************************************************************************************************************************************************************
// * Data window - debugging
// *************************************************************************************************************************************************************************************************************************************************************************
price_stop = strategy.position_size > 0 ? price_stop_long : price_stop_short

// *************************************************************************************************************************************************************************************************************************************************************************
// * Buy/Sell signals
// *************************************************************************************************************************************************************************************************************************************************************************
w_total_long = weight_total(long_signal1, long_signal2, long_signal3, long_signal4, long_signal5)
w_total_short = weight_total(short_signal1, short_signal2, short_signal3, short_signal4, short_signal5)
// *************************************************************************************************************************************************************************************************************************************************************************
// * Stop loss targets
// *************************************************************************************************************************************************************************************************************************************************************************
plot(series=(strategy.position_size > 0) ? price_stop_long : na, color=color.gray, style=plot.style_cross, linewidth=2, transp=30, title="Long Stop Loss")
plot(series=(strategy.position_size < 0) ? price_stop_short : na, color=color.gray, style=plot.style_cross, linewidth=2, transp=30, title="Short Stop Loss")
// *************************************************************************************************************************************************************************************************************************************************************************
// * TP targets
// *************************************************************************************************************************************************************************************************************************************************************************
plot(strategy.position_size > 0 or strategy.position_size < 0 ? nextTP : na, color=color.aqua, style=plot.style_cross, linewidth=2, transp=30, title="Next TP")
// *************************************************************************************************************************************************************************************************************************************************************************
```

> Detail

https://www.fmz.com/strategy/483683

> Last Modified

2025-02-25 11:29:23
