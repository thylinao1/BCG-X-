# Chatbot (CLI) — Brief Documentation

---

## What It Does
A **very simple, CSV-driven command-line chatbot** that prints selected columns from `FinAnalysis.csv` in response to **10 predefined financial questions**.  
It’s intentionally minimal and easy to grade — no machine learning, no web app, no functions — just `if / elif` logic and table output.


Limitations (Intentional Simplifications)

Exact phrasing only: Only recognizes the 10 listed questions (case-insensitive).
Anything else triggers: “This question isn’t in the predefined ones. I’ll connect you to an agent.”

No validation/guardrails:
Assumes the CSV is valid and complete (no checks for missing data or typos).

No calculations:
Strictly prints existing data — no CAGR, ratios, or growth computations.

Static prompts:
“Show latest for Microsoft/Tesla” are fixed examples for simplicity.

Local CLI only:
Runs in your terminal — no Flask/web interface, no API, no persistence.



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

>  show operating cash flow for the companies
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
>  show latest for microsoft
     Company  Fiscal Year  Total Revenue (USDm)  Net Income (USDm)
3  Microsoft         2024                245122              88136
>  show total liabilities for the companies
     Company  Fiscal Year  Total Liabilities (USDm)
0      Apple         2024                    308030
1      Apple         2023                    290437
2      Apple         2022                    302083
3  Microsoft         2024                    243686
4  Microsoft         2023                    205753
5  Microsoft         2022                    198298
6      Tesla         2024                     48390
7      Tesla         2023                     43009
8      Tesla         2022                     36440
>  which one should I invest in?
This question isn't in the 10 predefined ones. I'll connect you to an agent.
>  quit
Bye!
