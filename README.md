# Trader Behavior & Market Sentiment Analysis  
### Bitcoin Fear & Greed Index × Hyperliquid Historical Trades

##  Project Overview
This project analyzes how **Bitcoin market sentiment (Fear & Greed Index)** influences **trader behavior and performance** using historical trade data from Hyperliquid.

The goal is to move beyond basic PnL analysis and uncover:
- Behavioral biases during Fear and Greed regimes
- Differences between Retail traders and Whales
- Evidence of panic selling, FOMO buying, and contrarian strategies

---

##  Datasets Used

### 1. Bitcoin Market Sentiment Dataset
- `date` – Daily date
- `value` – Fear & Greed Index score (0–100)
- `classification` – Sentiment category  
  *(Extreme Fear, Fear, Neutral, Greed, Extreme Greed)*

### 2. Hyperliquid Historical Trade Data
- `Account` – Trader wallet address
- `Side` – Buy / Sell
- `Size USD` – Trade size in USD
- `Closed PnL` – Profit or loss per trade
- `Timestamp IST` – Trade execution time (IST)
- ~211,000 trade records

---

##  Methodology

### 1. Time-Series Alignment
- Trade timestamps were converted from **IST (DD-MM-YYYY HH:MM)** to daily dates.
- Sentiment data was already daily.
- Trades were **left-joined** with sentiment data to preserve all executions.

### 2. Feature Engineering
- Win / Loss indicators
- Buy / Sell behavior flags
- Daily account-level aggregation:
  - Total PnL
  - Win rate
  - Trade count
  - Total traded volume (USD)

### 3. Trader Segmentation
Traders were segmented using trade size (`Size USD`):
- **Retail** (small trades)
- **Mid**
- **Whale** (largest trades)

---

##  Key Results & Visual Insights

### 1. Sentiment vs Trader Profitability
- All sentiment regimes show **high PnL dispersion**
- **Fear and Extreme Fear** periods exhibit large upside and downside tails
- **Greed phases** show frequent extreme losses → overconfidence and overtrading

 *Conclusion:*  
Market sentiment strongly affects the **risk distribution**, not just average returns.

---

### 2. Trader Type Performance (Retail vs Whales)

**Observed Pattern from Bar Chart Output:**
- Retail traders show consistently low average PnL
- Mid-sized traders perform better during Fear
- **Whales significantly outperform during Fear and Extreme Greed**

 *Insight:*  
Large traders tend to accumulate during Fear, while smaller traders react emotionally.

---

### 3. Behavioral Bias Detection

####  Panic Selling
- SELL trades during Fear regimes show **negative average PnL**
- Indicates emotionally driven exits at unfavorable prices

####  FOMO Buying
- BUY trades during Extreme Greed produce weaker returns
- Suggests late entries driven by momentum chasing

---

### 4. Contrarian Trader Identification
A small subset of trader accounts consistently generated high cumulative profits by:
- Profiting during Fear regimes
- Remaining profitable even during Greed extremes

 *Key takeaway:*  
Market efficiency is driven by a minority of sentiment-agnostic, disciplined traders.

---

##  Actionable Trading Insights

- Avoid aggressive exposure during **Extreme Greed**
- Reduce SELL activity during **Fear** to avoid panic exits
- Monitor **Whale behavior during Fear** as accumulation signals
- Track **contrarian accounts** as early indicators of trend reversals

---

##  Limitations
- Leverage impact was not explicitly modeled
- No transaction cost or slippage adjustment
- Strategy performance not backtested

---

##  Future Improvements
- Add leverage sensitivity analysis
- Compute Sharpe ratio and drawdowns by sentiment regime
- Backtest contrarian strategies
- Model volatility-adjusted returns

---

##  Tools & Technologies
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Google Colab

---

##  Author
**Lakshmi Bhargavi Duvvuri**  


