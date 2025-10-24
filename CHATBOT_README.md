# AI-Powered Financial Chatbot for 10-K Analysis

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Handling-green.svg)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![BCG X](https://img.shields.io/badge/BCG%20X-GenAI%20Consulting-red.svg)](https://www.bcg.com/)

## 🤖 Project Overview

An **interactive rule-based financial chatbot** that transforms complex 10-K financial data into accessible, conversational insights. This project demonstrates practical AI application in finance by building a query-response system that retrieves and presents financial metrics for Microsoft, Tesla, and Apple (FY 2022–2024).

**Context:** Developed as part of BCG X GenAI Consulting virtual experience program, simulating real-world AI chatbot development for Global Finance Corp.'s digital transformation initiative.

---

## 🎯 Objectives

- **Build** a rule-based conversational interface for financial data queries
- **Implement** intelligent query matching and data retrieval logic
- **Transform** static financial datasets into interactive user experiences
- **Demonstrate** foundational AI chatbot development principles
- **Provide** instant access to key financial metrics through natural language queries

---

## ✨ Key Features

### Core Functionality
- **10 Predefined Financial Queries** covering revenue, profitability, cash flow, assets, and liabilities
- **Company-Specific Queries** for targeted analysis (Microsoft, Tesla, Apple)
- **Multi-Year Data Access** spanning fiscal years 2022–2024
- **Graceful Error Handling** with fallback to human agent escalation
- **Case-Insensitive Processing** for improved user experience

### Supported Query Types
| Query Category | Example |
|----------------|---------|
| **Revenue Analysis** | "what is the revenue for the companies" |
| **Profitability Metrics** | "what is the net income for the companies" |
| **Cash Flow Insights** | "show operating cash flow for the companies" |
| **Balance Sheet Data** | "show total assets for the companies" |
| **Leverage Analysis** | "show total liabilities for the companies" |
| **Multi-Metric View** | "show company, year, revenue, net income" |
| **Data Exploration** | "list companies" / "list years" |
| **Latest Financials** | "show latest for microsoft" / "show latest for tesla" |

---

## 🛠️ Technical Architecture

### Technology Stack
- **Python 3.10+** – Core programming language
- **Pandas** – Financial data manipulation and retrieval
- **Jupyter Notebook** – Interactive development environment
- **IPython** – Enhanced interactive computing

### Design Pattern: Rule-Based Logic
```python
# Core chatbot architecture
if user_query == "what is the revenue for the companies":
    return df[["Company", "Fiscal Year", "Total Revenue (USDm)"]]
elif user_query == "show latest for microsoft":
    sub = df[df["Company"] == "Microsoft"]
    latest = sub[sub["Fiscal Year"] == sub["Fiscal Year"].max()]
    return latest[["Company", "Fiscal Year", "Total Revenue (USDm)", "Net Income (USDm)"]]
else:
    return "This question isn't in the 10 predefined ones. I'll connect you to an agent."
```

### State Management
- **Session Persistence:** Single conversation loop with continuous query processing
- **Data Caching:** Financial dataset loaded once at initialization
- **Query Normalization:** Input standardization via `.strip().lower()`

---

## 📊 Data Integration

### Source Data
- **Dataset:** `10-K_Financials__USD_millions_.csv`
- **Companies:** Apple, Microsoft, Tesla
- **Time Period:** Fiscal Years 2022–2024
- **Metrics:** 
  - Total Revenue
  - Net Income
  - Total Assets
  - Total Liabilities
  - Operating Cash Flow

### Data Structure
```python
# Sample data schema
Company | Fiscal Year | Total Revenue (USDm) | Net Income (USDm) | Total Assets (USDm) | ...
--------|-------------|---------------------|-------------------|---------------------|----
Apple   | 2024        | 391,035             | 93,736            | 364,980             | ...
```

---

## 🚀 How It Works

### User Interaction Flow
```
1. Chatbot displays 10 available queries
2. User enters query (case-insensitive)
3. System matches query to predefined response logic
4. Chatbot retrieves relevant data from DataFrame
5. Results displayed in formatted table
6. Loop continues until user types "exit" or "quit"
```

### Error Handling Strategy
- **Unrecognized Queries:** Polite escalation message directing to human support
- **Input Exceptions:** Graceful handling of EOF and keyboard interrupts
- **Data Validation:** Pre-loaded dataset ensures query responses always available

---

## 💻 Running the Chatbot

### Prerequisites
```bash
pip install pandas jupyter ipython
```

### Execution Steps
```bash
# Clone repository
git clone <repository-url>
cd financial-chatbot

# Ensure data file is in same directory
# File: 10-K_Financials__USD_millions_.csv

# Launch Jupyter Notebook
jupyter notebook ChatBot.ipynb

# Run all cells to start chatbot
```

### Sample Interaction
```
Chatbot. Type one of the 10 questions below, or 'exit'.

1) what is the revenue for the companies
2) what is the net income for the companies
[...additional queries...]

> show latest for microsoft
     Company  Fiscal Year  Total Revenue (USDm)  Net Income (USDm)
3  Microsoft         2024                245122              88136

> quit
Bye!
```

---

## 📈 Example Outputs

### Query: "show operating cash flow for the companies"
```
     Company  Fiscal Year  Cash Flow from Operating Activities (USDm)
0      Apple         2024                                      118254
1      Apple         2023                                      110543
2      Apple         2022                                      122151
3  Microsoft         2024                                      118548
4  Microsoft         2023                                       87582
5  Microsoft         2022                                       89035
6      Tesla         2024                                       14923
7      Tesla         2023                                       13256
8      Tesla         2022                                       14724
```

---

## 🎓 AI Development Principles Demonstrated

### 1. Rule-Based Logic
- **If-Else Decision Trees:** Deterministic query-response mapping
- **Predefined Query Matching:** Exact string matching for reliable responses
- **Scalable Architecture:** Easy to extend with additional queries

### 2. State Management
- **Conversation Loop:** Maintains context across multiple queries
- **Session Memory:** Persistent data access throughout interaction
- **Clean Exit Handling:** User-controlled termination

### 3. Error Handling & UX
- **Graceful Degradation:** Unrecognized queries escalate to human agent
- **User Guidance:** Clear menu of available queries upfront
- **Input Flexibility:** Case-insensitive processing improves accessibility

### 4. Data-Driven Responses
- **Dynamic Retrieval:** Real-time data filtering based on query parameters
- **Structured Output:** Formatted tables for readability
- **Multi-Dimensional Filtering:** Company and year-specific queries

---

## 🔮 Future Enhancements

This prototype establishes the foundation for advanced features:

### Natural Language Processing (NLP)
- Implement fuzzy matching for query variations
- Add synonym recognition (e.g., "earnings" = "net income")
- Support partial query matching

### Machine Learning Integration
- Learn from user interactions to improve responses
- Predict next likely query based on conversation history
- Personalized financial insights

### Enhanced Analytics
- Calculate financial ratios on-demand (P/E, ROE, debt-to-equity)
- Year-over-year growth comparisons
- Trend analysis and forecasting

### User Interface Upgrades
- Web-based interface using Flask/Streamlit
- Data visualizations (charts, graphs)
- Export functionality for reports

---

## 📂 Project Structure

```
financial-chatbot/
├── ChatBot.ipynb                           # Main chatbot implementation
├── 10-K_Financials__USD_millions_.csv      # Financial dataset
├── README.md                               # Project documentation
└── requirements.txt                        # Python dependencies
```

---

## 🎯 Business Impact

### Value Proposition
- **Accessibility:** Democratizes financial data access for non-technical stakeholders
- **Efficiency:** Instant retrieval vs. manual 10-K document review
- **Scalability:** Foundation for enterprise-wide AI chatbot deployment
- **Cost Reduction:** Automates routine financial queries, reducing analyst workload

### Use Cases
- **Investment Research:** Quick company performance comparisons
- **Financial Planning:** Historical trend analysis for forecasting
- **Client Reporting:** On-demand metrics for stakeholder presentations
- **Due Diligence:** Rapid financial health assessment

---

## 🎓 Skills Demonstrated

### Technical Skills
- **Python Programming:** Control flow, data structures, function design
- **Data Engineering:** CSV parsing, DataFrame manipulation, filtering
- **Software Architecture:** Rule-based system design, state management
- **User Interface Design:** Interactive command-line interface development

### Business Skills
- **Financial Analysis:** Understanding of 10-K metrics and their significance
- **Product Thinking:** Translating user needs into technical requirements
- **Communication:** Clear documentation and error messaging
- **Problem Solving:** Graceful handling of edge cases

---

## 🔒 Limitations & Considerations

### Current Constraints
- **Fixed Query Set:** Limited to 10 predefined questions
- **Exact Matching Required:** No support for query variations or typos
- **No Learning Capability:** Static rule-based logic (no ML adaptation)
- **Text-Only Output:** No visualizations or graphical representations

### Production Considerations
- **Security:** Add authentication for sensitive financial data
- **Scalability:** Implement database backend for larger datasets
- **Monitoring:** Add logging for query analytics and system health
- **Compliance:** Ensure adherence to financial data disclosure regulations

---

## 📚 References & Resources

- **BCG X GenAI Consulting:** Virtual experience program curriculum
- **SEC EDGAR Database:** Source of 10-K financial data
- **Pandas Documentation:** Data manipulation techniques
- **Chatbot Design Principles:** Rule-based conversational AI patterns

---

## 📝 License

This project is for educational and portfolio demonstration purposes.

---

## 👤 Author

**[Your Name]**  
*AI/ML Enthusiast | Financial Technology Developer*

[LinkedIn](your-linkedin-url) | [Portfolio](your-portfolio-url) | [Email](mailto:your-email)

---

## 🙏 Acknowledgments

- **BCG X** – GenAI Consulting program for project framework and guidance
- **Global Finance Corp.** – Simulated client providing business context
- **Anthropic** – AI development best practices and consultation

---

## 🤝 Contributing

This is a personal portfolio project, but feedback and suggestions are welcome! Feel free to:
- Open issues for bugs or enhancement ideas
- Fork the repository for your own experimentation
- Share your chatbot improvements or extensions

---

*Note: This chatbot is a prototype demonstrating foundational AI principles. It uses rule-based logic suitable for controlled query sets. Production implementations would incorporate NLP, machine learning, and robust security measures.*
