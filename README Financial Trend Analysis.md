# Financial Trend Analysis: Microsoft, Tesla & Apple (2022–2024)

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green.svg)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 📊 Project Overview

A comprehensive financial analysis of three Fortune 500 companies—**Microsoft**, **Tesla**, and **Apple**—using audited 10-K filings from fiscal years 2022–2024. This project demonstrates data extraction, financial modeling, and strategic insight generation for AI-powered financial applications.

**Context:** Completed as part of BCG X GenAI Consulting virtual experience, simulating real-world data science work for Global Finance Corp.'s AI chatbot development.

---

## 🎯 Objectives

- **Extract** key financial metrics from SEC 10-K filings (Total Revenue, Net Income, Total Assets, Total Liabilities, Operating Cash Flow)
- **Engineer** financial indicators including YoY growth rates, profit margins, leverage ratios, and 2-year CAGR
- **Analyze** trends to identify company financial health, growth trajectories, and operational efficiency
- **Visualize** multi-year performance for comparative analysis
- **Deliver** actionable insights for AI model integration and investment decision-making

---

## 🔍 Key Findings

### Microsoft
- **Revenue CAGR:** +11.2% | **Net Income CAGR:** +10.1%
- **Operational Excellence:** 45% cash flow conversion, 35% net margins
- **Strategic Position:** Cloud & AI expansion driving consistent growth with low leverage (~48%)

### Tesla
- **Revenue CAGR:** +9.5% | **Net Income CAGR:** -24.6%
- **Growth vs. Profitability:** Strong top-line growth offset by margin compression
- **Operational Focus:** Flat cash flow signals efficiency challenges amid capacity expansion

### Apple
- **Revenue CAGR:** -0.4% | **Net Income CAGR:** -3.1%
- **Mature & Resilient:** Stable cash generation (~30% OpCF/Revenue), strong margins (~25%)
- **Capital Strategy:** High leverage (~84%) reflects shareholder return focus, not distress

### Comparative Summary
| Metric | Microsoft | Tesla | Apple |
|--------|-----------|-------|-------|
| **Revenue Growth** | +11% | +9% | -0.4% |
| **Profitability** | +10% | -25% | -3% |
| **Cash Efficiency** | 45% | 16% | 30% |
| **Margin Quality** | 35% | 13% | 25% |

**Investment Thesis:** MSFT = sustainable growth leader | AAPL = cash flow powerhouse | TSLA = high-variance innovation play

---

## 🛠️ Technical Stack

- **Python 3.8+** – Core programming language
- **Pandas** – Data manipulation and financial calculations
- **NumPy** – Numerical computations
- **Matplotlib** – Data visualization
- **Jupyter Notebook** – Interactive analysis environment

---

## 📁 Project Structure

```
├── Financial_Trend_Analysis_2022_2024.ipynb  # Main analysis notebook
├── 10-K_Financials__USD_millions_.csv        # Extracted financial data
├── FinAnalysis.csv                            # Processed output dataset
└── README.md                                  # Project documentation
```

---

## 🚀 Methodology

### 1. Data Collection
- Manually extracted data from SEC EDGAR database (official 10-K filings)
- Focused on audited financial statements: Income Statement, Balance Sheet, Cash Flow Statement
- Compiled 3 years of data per company (FY 2022–2024)

### 2. Data Preparation & Feature Engineering
```python
# Year-over-year growth calculations
df['Revenue Growth (%)'] = df.groupby('Company')['Total Revenue'].pct_change() * 100

# Profitability metrics
df['Net Margin (%)'] = (df['Net Income'] / df['Total Revenue']) * 100

# Cash flow efficiency
df['OpCF/Revenue (%)'] = (df['Cash Flow from Operating Activities'] / df['Total Revenue']) * 100

# Leverage analysis
df['Leverage Ratio'] = df['Total Liabilities'] / df['Total Assets']
```

### 3. Advanced Analytics
- **CAGR Calculation:** 2-year compound annual growth rates for revenue, net income, assets, and operating cash flow
- **Comparative Analysis:** Cross-company performance benchmarking
- **Trend Visualization:** Multi-year charts for key financial indicators

### 4. Insight Generation
- Synthesized quantitative findings into strategic business narratives
- Identified financial health indicators, operational efficiency patterns, and risk factors
- Provided data-driven recommendations suitable for AI chatbot training

---

## 📈 Sample Visualizations

The notebook includes:
- Revenue trend analysis (2022–2024)
- Net income trajectory comparisons
- Cash flow efficiency metrics
- Leverage ratio evolution

---

## 💡 Business Impact

This analysis directly supports:
- **AI Model Training:** Clean, structured financial data for chatbot knowledge base
- **Investment Research:** Objective performance metrics for portfolio decisions
- **Risk Assessment:** Leverage and profitability trends for credit analysis
- **Strategic Planning:** Growth patterns and operational benchmarks

---

## 🏃 How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib jupyter
```

### Execution
```bash
# Clone the repository
git clone <repository-url>

# Navigate to project directory
cd financial-trend-analysis

# Launch Jupyter Notebook
jupyter notebook Financial_Trend_Analysis_2022_2024.ipynb
```

---

## 📚 Data Sources

- **SEC EDGAR Database** – Official 10-K filings
  - [Microsoft 10-K Filings](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=0000789019&type=10-K)
  - [Tesla 10-K Filings](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=0001318605&type=10-K)
  - [Apple 10-K Filings](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=0000320193&type=10-K)

---

## 🎓 Skills Demonstrated

- **Financial Analysis:** 10-K interpretation, ratio analysis, trend identification
- **Data Engineering:** ETL processes, feature engineering, data normalization
- **Python Programming:** Pandas, NumPy, Matplotlib proficiency
- **Business Intelligence:** Translating data into actionable insights
- **Documentation:** Clear, professional technical communication

---

## 🙏 Acknowledgments

- **BCG X** – GenAI Consulting virtual experience program
- **SEC** – Public company financial disclosure database
