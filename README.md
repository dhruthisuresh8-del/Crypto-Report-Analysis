# crypto-report

**Gold Standard vs. Code Standard: Decoding Crypto's Place in Modern Portfolios**

A quantitative finance report published as a static website.

## 📊 About

This report investigates Bitcoin's claim as "digital Gold" using:
- Descriptive statistics (mean return, std. dev, skewness, kurtosis)
- Correlation analysis across BTC, ETH, Gold, and S&P 500
- Probability and conditional probability analysis
- Value at Risk (VaR) via Historical Simulation and Variance-Covariance methods
- Hypothesis testing (two-sample t-test)

**Data period:** June 2023 – January 2025  
**Author:** Dhruthi Suresh · Master of Finance · S4103956

## 🚀 Live Site

Published via GitHub Pages: `https://<your-username>.github.io/crypto-report`

## 📁 Structure

```
crypto-report/
├── index.html       # Main report page
├── css/
│   └── style.css    # All styles
├── js/
│   └── main.js      # Scroll animations
└── README.md
```

## 🖥️ Run Locally

No build step needed — just open `index.html` in a browser, or serve with:

```bash
npx serve .
# or
python3 -m http.server 8080
```

## 🌐 Deploy to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your site will be live at `https://<username>.github.io/crypto-report`

## Key Findings

| Finding | Result |
|---|---|
| BTC–ETH Correlation | 0.96 (speculative, not safe-haven) |
| BTC–Gold Correlation | 0.71 (weak hedge relationship) |
| VaR 99% (75% Gold / 25% BTC) | AUD 4,259 |
| Hypothesis test p-value | 0.115 (fail to reject H₀) |

> Bitcoin is not yet a reliable store of value akin to Gold. Its extreme volatility, inconsistent crisis performance, and weak correlation with traditional hedges classify it as a speculative asset best used for diversification, not capital preservation.
