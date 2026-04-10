# 📊 Gold Standard vs. Code Standard: Decoding Crypto's Place in Modern Portfolios

> A quantitative finance research report examining Bitcoin's viability as "digital Gold" through statistical analysis, risk modelling, and hypothesis testing.

**Author:** Dhruthi Suresh · Master of Finance · S4103956  
**Data Period:** June 2023 – January 2025  
**Assets Analysed:** Bitcoin (BTC), Ethereum (ETH), Gold, S&P 500  
**Published:** [Live on GitHub Pages](https://your-username.github.io/crypto-report)

---

## 📌 Table of Contents

1. [Project Overview](#project-overview)
2. [Research Question](#research-question)
3. [Literature Review Summary](#literature-review-summary)
4. [Data & Methodology](#data--methodology)
5. [Descriptive Statistics](#descriptive-statistics)
6. [Correlation Analysis](#correlation-analysis)
7. [Probability Analysis](#probability-analysis)
8. [Value at Risk (VaR)](#value-at-risk-var)
9. [Hypothesis Testing](#hypothesis-testing)
10. [Key Findings](#key-findings)
11. [Investment Recommendations](#investment-recommendations)
12. [Project Structure](#project-structure)
13. [Run Locally](#run-locally)
14. [Deploy to GitHub Pages](#deploy-to-github-pages)
15. [References](#references)

---

## Project Overview

Over the past decade, Bitcoin has been widely labelled as **"digital Gold"** — a narrative suggesting it could serve as a modern store of value, inflation hedge, and safe-haven asset in the same way physical Gold has for centuries. This report rigorously stress-tests that claim using quantitative financial methods.

The report was produced as part of a Master of Finance programme and analyses daily price data across four assets — **Bitcoin, Ethereum, Gold, and the S&P 500** — over an 18-month window from June 2023 to January 2025. Statistical tools including correlation matrices, VaR models, probability analysis, and t-tests are applied to determine whether Bitcoin genuinely behaves like Gold or whether the "digital Gold" narrative is more marketing than mathematics.

---

## Research Question

> **Does Bitcoin behave like Gold as a store of value and safe-haven asset, or does it behave like a speculative, high-risk financial instrument?**

This question is examined through five analytical lenses:
- Statistical return characteristics (mean, volatility, skewness, kurtosis)
- Asset co-movement (correlation matrices)
- Likelihood of positive/negative returns under different market conditions (probability analysis)
- Downside risk exposure (Value at Risk)
- Mean return equivalence (hypothesis testing)

---

## Literature Review Summary

Ten scholarly articles and financial commentaries from *The Economist* and peer-reviewed journals were reviewed to establish an academic foundation. The consensus is **divided but leans sceptical** of Bitcoin's safe-haven status:

| Author(s) | Year | Core Position |
|---|---|---|
| Baur, Hong & Lee | 2018 | Bitcoin's volatility far exceeds Gold; unsuitable as a safe-haven |
| Corbet et al. | 2019 | Bitcoin fails to demonstrate consistent safe-haven properties in financial crises |
| Dyhrberg | 2016 | Bitcoin has some hedging capability against currency fluctuations, but lacks stability |
| Cheah & Fry | 2015 | Bitcoin is prone to speculative price bubbles with no clear intrinsic value |
| Yermack | 2015 | Bitcoin fails as a medium of exchange, store of value, and unit of account |
| Shahzad et al. | 2019 | Bitcoin offers some diversification benefits, but these are inconsistent across market conditions |
| Bouri et al. | 2017 | Cryptocurrencies should be treated as speculative assets, not stable stores of value |
| Kristoufek | 2018 | Bitcoin displays both speculative and safe-haven qualities at different times; high volatility undermines consistency |
| Zhang et al. | 2021 | Gold outperforms Bitcoin as a hedge under inflationary conditions |
| *The Economist* | 2023/2024 | Bitcoin's price instability and lack of regulatory framework expose investors to significant risk |

**Overall academic position:** While Bitcoin possesses *some* characteristics that superficially resemble Gold (finite supply, decentralisation), the weight of evidence classifies it as a **speculative asset**, not a reliable store of value.

---

## Data & Methodology

### Data Sources
Daily closing price data was collected for the following assets over the period **June 2023 to January 2025** (approximately 400 trading days):

- **Bitcoin (BTC)** — via CoinGecko / Yahoo Finance
- **Ethereum (ETH)** — via CoinGecko / Yahoo Finance
- **Gold (XAU/USD)** — spot price
- **S&P 500 (^GSPC)** — index closing price

### Return Calculation
Daily log returns were computed as:

```
r_t = ln(P_t / P_{t-1})
```

Log returns are preferred over simple returns for their time-additivity and better approximation of normality over short intervals.

### Analytical Methods Applied

| Method | Purpose |
|---|---|
| Descriptive Statistics | Characterise return distribution per asset |
| Correlation Matrix | Measure co-movement between asset pairs |
| Positive Return Probability | Assess likelihood of daily gains |
| Conditional Probability | Measure safe-haven behaviour under stress |
| Historical Simulation VaR | Non-parametric downside risk estimate |
| Variance-Covariance VaR | Parametric downside risk estimate |
| Two-Sample t-Test | Formally test equality of mean returns |

---

## Descriptive Statistics

Daily return statistics across all four assets confirm the fundamental difference in risk profiles between traditional and digital assets:

| Asset | Mean Return | Std. Deviation | Skewness | Kurtosis |
|---|---|---|---|---|
| Gold | 0.000586 | 0.01883 | −0.002 | 3.04 |
| S&P 500 | 0.000809 | 0.01359 | −0.660 | 5.97 |
| Bitcoin | 0.003491 | 0.03090 | +0.390 | 3.60 |
| Ethereum | 0.003685 | 0.03124 | +0.420 | 4.11 |

### Interpretation

**Mean Returns:** Bitcoin and Ethereum deliver significantly higher average daily returns (~0.35% and ~0.37% respectively) compared to Gold (~0.06%) and the S&P 500 (~0.08%). However, this return premium comes at a steep cost in volatility.

**Standard Deviation:** Cryptocurrencies exhibit standard deviations more than **1.6× higher** than Gold and **2.3× higher** than the S&P 500. This confirms that the higher returns of crypto assets are accompanied by substantially greater risk — a classic risk-return trade-off.

**Skewness:**
- Gold's near-zero skewness (−0.002) indicates a near-symmetric return distribution — consistent with a mature, liquid market.
- The S&P 500's negative skewness (−0.66) reflects the well-documented equity market tendency for sharper drawdowns than rallies.
- Both BTC (+0.39) and ETH (+0.42) display positive skewness, suggesting occasional large upside events — consistent with speculative bull-run behaviour.

**Kurtosis:**
- Gold's kurtosis of 3.04 is close to the normal distribution benchmark of 3.0, indicating relatively few extreme events.
- S&P 500's elevated kurtosis (5.97) reflects fat tails — periodic crash events beyond what a normal distribution would predict.
- Bitcoin (3.60) and Ethereum (4.11) show moderate excess kurtosis, indicating that extreme daily moves — both positive and negative — occur more frequently than normality assumes. This has direct implications for risk management and VaR model accuracy.

---

## Correlation Analysis

The correlation matrix below measures the linear co-movement of daily returns between all four assets:

|  | Gold | S&P 500 | ETH | BTC |
|---|---|---|---|---|
| **Gold** | 1.00 | 0.81 | 0.73 | 0.71 |
| **S&P 500** | 0.81 | 1.00 | 0.86 | 0.83 |
| **ETH** | 0.73 | 0.86 | 1.00 | 0.96 |
| **BTC** | 0.71 | 0.83 | 0.96 | 1.00 |

### Interpretation

**BTC–ETH (0.96):** The near-perfect correlation between Bitcoin and Ethereum confirms they move almost in lockstep. This is consistent with the broader cryptocurrency market behaviour — both assets respond to the same macro catalysts: regulatory news, exchange events, and speculative sentiment cycles. This high intra-crypto correlation means holding both assets provides negligible diversification benefit within a crypto allocation.

**BTC–Gold (0.71):** A correlation of 0.71 between Bitcoin and Gold is moderate — not the near-zero or negative relationship you would expect of a true safe-haven. If Bitcoin were genuinely "digital Gold," we would expect it to rise (or hold steady) when Gold rises, and fall when Gold falls, in a consistent and predictable pattern. A 0.71 correlation with Gold (and simultaneously a 0.83 correlation with the S&P 500) suggests Bitcoin behaves more like a **risk-on equity asset** than a defensive commodity.

**BTC–S&P 500 (0.83):** Bitcoin's stronger correlation with equities than with Gold is a critical finding. It suggests that institutional adoption of Bitcoin has tied its fortunes more tightly to the broader risk appetite of equity markets — meaning Bitcoin tends to fall when investors flee risk assets during market downturns, the exact moment a safe-haven should hold its value.

**Gold–S&P 500 (0.81):** Interestingly, Gold also shows a high correlation with equities during this specific period (2023–2025), which reflects the atypical macro environment of post-pandemic monetary tightening, where traditional safe-haven dynamics were somewhat disrupted.

---

## Probability Analysis

### Unconditional Positive Return Probability

Over the analysis period, the probability of a positive daily return was:

| Asset | P(positive return) |
|---|---|
| Bitcoin | 52.6% |
| S&P 500 | 52.6% |
| Gold | 52.6% |

All three assets produced positive daily returns roughly **52.6% of the time** — slightly better than a coin flip. This equivalence is noteworthy: despite Bitcoin's dramatically higher volatility and return, the *frequency* of positive days is identical to Gold and the S&P 500. This confirms that Bitcoin's higher average return is driven by the **magnitude** of its up-days, not the frequency — a hallmark of speculative, momentum-driven assets.

### Conditional Probabilities

Conditional probabilities were computed to test whether Bitcoin and Ethereum exhibit safe-haven behaviour — i.e., whether they tend to hold value or rise when traditional assets fall:

| Condition | Probability |
|---|---|
| P(BTC falls \| Gold falls) | 47.4% |
| P(ETH rises \| S&P 500 falls) | 28.5% |

**P(BTC↓ \| Gold↓) = 47.4%:** When Gold falls, there is nearly a 50/50 chance Bitcoin also falls. This near-random relationship means Bitcoin provides **no reliable safe-haven signal** relative to Gold. A true Gold-equivalent should either be uncorrelated with Gold's movements or positively correlated in a consistent, directional way.

**P(ETH↑ \| S&P 500↓) = 28.5%:** Ethereum rises only 28.5% of the time when the S&P 500 falls — meaning it declines or stays flat the majority of the time markets sell off. This classifies Ethereum firmly as a **procyclical, risk-on asset**, not a defensive holding.

---

## Value at Risk (VaR)

VaR was calculated for a hypothetical portfolio allocated **75% Gold and 25% Bitcoin** over the last 252 business days (approximately one trading year), representing a portfolio with a moderate crypto tilt.

### Methods Used

**1. Historical Simulation:** Applies the actual empirical distribution of past returns to estimate future losses. No distributional assumptions are made, making it robust to non-normal return behaviour — particularly relevant given crypto's fat tails.

**2. Variance-Covariance (Parametric):** Assumes returns follow a normal distribution and uses the portfolio's estimated mean and standard deviation to compute loss thresholds. Simpler but potentially underestimates tail risk in volatile assets.

### Results (AUD)

| Method | VaR at 95% Confidence | VaR at 99% Confidence |
|---|---|---|
| Historical Simulation | $3,056.46 | $4,259.47 |
| Variance-Covariance | $3,057.04 | $4,260.01 |

### Interpretation

Both methods produce near-identical results, which increases confidence in the estimates. The close agreement between the parametric and non-parametric methods suggests that, over this particular period, the return distributions were sufficiently well-behaved for the variance-covariance model's normality assumption to hold reasonably.

At the **99% confidence level**, this portfolio could lose more than **AUD 4,259** in a single day — meaning that on approximately 1 in every 100 trading days, losses would exceed this threshold. Annualised, this equates to roughly 2–3 such extreme loss events per year.

The 25% Bitcoin allocation is directly responsible for the elevated VaR relative to a pure Gold portfolio. Bitcoin's standard deviation (~3.09% daily) is approximately 1.64× that of Gold (~1.88%), and its periodic extreme moves disproportionately inflate tail risk in any portfolio where it features.

---

## Hypothesis Testing

A two-sample t-test was conducted to formally evaluate whether the mean daily returns of Bitcoin and Gold are statistically distinguishable over the analysis period.

### Hypotheses

```
H₀ (Null):        μ_BTC = μ_Gold   (mean returns are equal)
H₁ (Alternative): μ_BTC ≠ μ_Gold   (mean returns are not equal)
Significance level: α = 0.05 (two-tailed)
```

### Results

| Statistic | Value |
|---|---|
| t-statistic | 1.577 |
| p-value | 0.115 |
| Decision | Fail to Reject H₀ |

### Interpretation

Since **p = 0.115 > 0.05**, we fail to reject the null hypothesis. There is insufficient statistical evidence at the 5% significance level to conclude that Bitcoin and Gold have meaningfully different mean daily returns over this period.

**What this means — and what it doesn't:**  
This result should not be misread as evidence that Bitcoin and Gold are equivalent investments. A failure to reject H₀ does not confirm H₀ — it merely reflects that the observed difference in means was not statistically significant given the sample size and variance. In fact, Bitcoin's raw mean return (0.003491) is approximately **6× higher** than Gold's (0.000586). The reason this difference failed to reach significance is Bitcoin's enormous standard deviation (~0.031), which widens the confidence intervals around its mean estimate substantially — a statistical consequence of high volatility obscuring the signal.

In practical terms: Bitcoin may well have a higher expected return than Gold, but its volatility makes that return **unpredictable and unreliable** on a day-to-day basis — which is itself a fundamental argument against its use as a stable store of value.

---

## Key Findings

| # | Finding |
|---|---|
| 1 | Bitcoin's correlation with Gold (0.71) is significantly weaker than its correlation with Ethereum (0.96) and the S&P 500 (0.83), suggesting it behaves more like a risk-on equity than a safe-haven commodity |
| 2 | Both BTC and ETH deliver higher average daily returns than Gold and the S&P 500, but at more than double the daily volatility |
| 3 | Bitcoin falls ~47% of the time when Gold falls — close to random, offering no reliable hedging signal |
| 4 | Ethereum rises only 28.5% of the time when the S&P 500 falls, confirming its procyclical nature |
| 5 | A 75/25 Gold–Bitcoin portfolio faces a daily loss exposure of over AUD 4,259 at the 99% confidence level |
| 6 | The hypothesis test fails to statistically distinguish Bitcoin and Gold mean returns — but this is a consequence of Bitcoin's high volatility, not evidence of equivalence |
| 7 | Bitcoin's positive skewness and moderate kurtosis are consistent with a speculative, event-driven asset, not a stable value store |

---

## Investment Recommendations

Based on the quantitative findings, the following recommendations are made for institutional investors and policymakers:

### For Institutional Investors

**🔴 Do not use Bitcoin as a primary inflation hedge.**  
Its inconsistent correlation with Gold and tendency to fall alongside risk assets during market downturns make it unreliable for capital preservation purposes.

**🟡 Treat Bitcoin as a speculative satellite allocation.**  
A small portfolio allocation (commonly cited guidance ranges from 1–5%) may provide diversification benefits through its non-traditional return profile, but position sizing must account for its elevated VaR contribution.

**🟢 Maintain Gold as the core defensive asset.**  
Gold's lower volatility, more symmetric return distribution, and centuries of established safe-haven credibility make it the more reliable hedge against macroeconomic uncertainty.

**🔵 Distinguish between BTC and ETH.**  
Ethereum's utility-driven value proposition (smart contracts, DeFi infrastructure) means it behaves differently from Bitcoin in certain market regimes. However, their near-perfect correlation (0.96) means they offer minimal diversification from each other within a portfolio.

### For Policymakers

**📋 Classify cryptocurrencies as speculative financial instruments**, subject to regulatory frameworks commensurate with their risk profile — distinct from commodities like Gold or regulated securities like equities.

**🔍 Require enhanced disclosure** from institutional products (ETFs, funds) that hold cryptocurrency, given VaR metrics that substantially exceed those of traditional asset classes.

---

## Project Structure

```
crypto-report/
│
├── index.html          # Full report as a static web page
│
├── css/
│   └── style.css       # Styling (dark/gold editorial theme)
│
├── js/
│   └── main.js         # Scroll-triggered animations
│
└── README.md           # This file
```

No frameworks, no build tools, no dependencies — pure HTML, CSS, and vanilla JavaScript. Opens directly in any browser.

---

## Run Locally

```bash
# Clone the repository
git clone https://github.com/your-username/crypto-report.git
cd crypto-report

# Option 1: Open directly
open index.html

# Option 2: Serve locally
npx serve .

# Option 3: Python server
python3 -m http.server 8080
# Then visit http://localhost:8080
```

---

## Deploy to GitHub Pages

1. Push this repository to GitHub
2. Navigate to **Settings → Pages**
3. Under *Source*, select `main` branch and `/ (root)` folder
4. Click **Save**
5. Your report will be live at:

```
https://your-username.github.io/crypto-report
```

---

## References

- Baur, D. G., Hong, K., & Lee, A. D. (2018). Bitcoin: Medium of exchange or speculative assets? *Journal of International Financial Markets, Institutions and Money*, 54, 177–189.
- Bouri, E., Jain, A., Roubaud, D., & Das, D. (2017). Bitcoin as an alternative investment during global uncertainties. *Finance Research Letters*, 23, 233–238.
- Cheah, E. T., & Fry, J. (2015). Speculative bubbles in Bitcoin markets? *Economics Letters*, 130, 32–36.
- Corbet, S., Lucey, B., Urquhart, A., & Yarovaya, L. (2019). Cryptocurrencies as a financial asset. *International Review of Financial Analysis*, 62, 182–199.
- Dyhrberg, A. H. (2016). Bitcoin, gold and the dollar – A GARCH volatility analysis. *Finance Research Letters*, 16, 85–92.
- Kristoufek, L. (2018). On Bitcoin markets (in)efficiency and its evolution. *Physica A*, 503, 257–262.
- Selgin, G. (2015). Synthetic commodity money. *Journal of Financial Stability*, 17, 92–99.
- Shahzad, S. J. H., Bouri, E., Roubaud, D., & Kristoufek, L. (2019). Safe haven, hedge and diversification for G7 stock markets: Gold versus Bitcoin. *Economic Modelling*, 87, 212–224.
- The Economist. (2023, June). Bitcoin's identity crisis: Is it Gold 2.0 or a risky tech stock?
- The Economist. (2024, January). Why cryptocurrencies still aren't safe havens.
- Urquhart, A. (2016). The inefficiency of Bitcoin. *Economics Letters*, 148, 80–82.
- Yermack, D. (2015). Is Bitcoin a real currency? In *Handbook of Digital Currency*. Academic Press.
- Zhang, W., et al. (2021). Hedging capabilities of cryptocurrencies compared to gold amid inflationary pressures. *Finance Research Letters*.

---

*This report was prepared for academic purposes as part of a Master of Finance programme. It does not constitute financial advice.*
