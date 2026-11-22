# European Bank — Customer Churn Intelligence Dashboard

**Live app:** https://european-bank-churn-analysis-d4su7yebzrqdkcxrolqwpf.streamlit.app/

An interactive Streamlit dashboard that finds which bank customers are most likely to leave, and why. It covers 10,000 customers in France, Germany and Spain.

Built during my Data Analyst Internship at Unified Mentor (2026).

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C)

![Dashboard](docs/dashboard.png)

## The business question

About 1 in 5 customers left the bank. Which customers leave most, and where should a retention team focus first?

## Key findings

- **Age matters most.** Customers aged 46–60 churn at **51.1%**, against 7.6% for under-30s. In Germany this group churns at 67.3%.
- **Germany stands out.** Churn is **32.4%** in Germany, against 16.2% in France and 16.7% in Spain.
- **Inactive customers leave more.** Inactive members churn at **26.9%**, against 14.3% for active members.
- **Two products is the sweet spot.** Churn is 27.7% with one product and 7.6% with two. It jumps to 82.7% with three, though only 326 customers hold three or more.
- **Credit score barely matters.** Churn is between 19.6% and 22.0% in every credit band.

Customers who left held **$185.6M in account balances**. That is money they kept at the bank, not revenue the bank earned.

## Churn risk score

A simple, transparent score from 0 to 100:

| Signal | Points |
|---|---|
| Inactive member | 30 |
| Age over 45 | 25 |
| 3 or more products | 25 |
| Zero balance | 10 |
| Credit score under 500 | 10 |

The weights were set by hand, not fitted to the data. Even so, the score separates customers well:

| Risk tier | Customers | Actually churned |
|---|---|---|
| High (55+) | 1,013 | **71.6%** |
| Medium (30–54) | 4,395 | 16.7% |
| Low (under 30) | 4,592 | 12.6% |

## What the dashboard shows

- **Filters:** geography, gender, age group, credit band, high-value and active-only toggles
- **Six tabs:** churn overview, geographic analysis, demographics, high-value customers, automated insights, raw data with CSV download
- Every KPI, chart and insight updates with the filters.

## Limitations

- **Sample data.** This appears to be a widely used public banking dataset, provided for the internship. It is not a real bank's records.
- **One snapshot in time.** There is no history, so the dashboard shows who left, not when or what triggered it.
- **The zero-balance signal points the wrong way.** Zero-balance customers churn *less* (13.8%) than average. Removing that signal would slightly improve the score.
- **Correlation, not cause.** The findings show which groups leave more, not why.

## Run it locally

```bash
git clone https://github.com/Vipsa2207/European-Bank-Churn-Analysis.git
cd European-Bank-Churn-Analysis
pip install -r requirements.txt
streamlit run app.py
```

## Project files

| File | What it is |
|---|---|
| `app.py` | The Streamlit dashboard |
| `European_Bank.csv` | 10,000 customer records |
| `requirements.txt` | Pinned library versions |

## Research paper

I authored a research paper on this project (JETIR paper ID 583670, accepted, not published).

- [Research paper, revised version (PDF)](docs/Research_Paper_Revised.pdf)
- [Stakeholder summary, revised version (PDF)](docs/Stakeholder_Summary_Revised.pdf)

The revised version (November 2026) corrects labels, figures and references in the version submitted to JETIR.

## How I built it

I used AI to help write the Python code. I framed the business question, checked every figure against the data, and wrote the findings.

## Author

**Vipsa Patel** — Data Analyst Intern, Unified Mentor · [LinkedIn](https://www.linkedin.com/in/vipsapatel)
