# Chatbot - Brief Documentation










# Chatbot - Brief Documentation

---

## What It Does
A **very simple, CSV-driven command-line chatbot** that prints selected columns from `FinAnalysis.csv` in response to **10 predefined financial questions**.  
It’s intentionally minimal and easy to grade — no machine learning, no web app, no functions — just `if / elif` logic and table output.


Limitations (Intentional Simplifications)

Exact phrasing only: Only recognizes the 10 listed questions (case-insensitive).
Anything else triggers: “This question isn’t in the predefined ones. I’ll connect you to an agent.”

Conversation Sample:
Chatbot. Type one of the 10 questions below, or 'exit'.

1) what is the revenue for the companies
2) what is the net income for the companies
3) show operating cash flow for the companies
4) show total assets for the companies
5) show total liabilities for the companies
6) show company, year, revenue, net income
7) list companies
8) list years
9) show latest for microsoft
10) show latest for tesla


Bye!
