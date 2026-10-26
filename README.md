# Data Analyst Internship Portfolio — [Your Name]

**ApexPlanet Data Analytics Internship** · Python · SQL · Power BI · Statistics

> **The one-line story:** I turned 1,000 raw, undocumented sales transactions into a statistically validated recommendation: **71% of revenue comes from 427 customers (45% of the base), and every one of them bought only once.**

**Live portfolio site:** https://YOUR-USERNAME.github.io/YourName-DataAnalyst-Internship-Portfolio/
**Final presentation deck:** [`deck/ApexPlanet_Final_Presentation.pptx`](deck/ApexPlanet_Final_Presentation.pptx)
**LinkedIn walkthrough video:** [add link]

---

## The Internship at a Glance

One dataset, four tasks, each building on the last. Every task answers the question the previous one raised.

| # | Task | The question it answered | Headline result | Repository |
|---|---|---|---|---|
| 1 | **Data Immersion & Wrangling** | Can this data be trusted? | 1,000 rows cleaned with zero data invented or dropped; 52 ambiguous Customer IDs flagged, not guessed | [Task 1 repo](https://github.com/YOUR-USERNAME/apexplanet-task1-data-wrangling) |
| 2 | **EDA & Business Intelligence** | What does the data look like? | Revenue is right-skewed (mean ₹1,39,399 vs median ₹1,08,594): a few large orders pull the average up | [Task 2 repo](https://github.com/YOUR-USERNAME/apexplanet-task2-eda-bi) |
| 3 | **Deep-Dive Analysis & Dashboarding** | Where does revenue actually come from? | Only 5.5% of customers ever reorder → RFM segmentation → one segment drives 71% of revenue | [Task 3 repo](https://github.com/YOUR-USERNAME/apexplanet-task3-deep-dive-dashboard) |
| 4 | **Data Storytelling & Statistical Validation** | Is the finding real, and what should the business do? | Welch's t-test: t = 29.22, p < 0.0001, Cohen's d = 1.94 → targeted win-back campaign | [Task 4 repo](https://github.com/YOUR-USERNAME/apexplanet-task4-storytelling-validation) |

---

## How the Story Unfolds

### 1. Wrangling: earn the right to analyse
The raw file had four quality problems: 20 missing ages, 13 missing cities, 9 orders sharing one Order ID, and 52 Customer IDs linked to more than one name. Each was handled by the least-destructive option: median fill for age, an honest `"Unknown"` for city, new IDs for duplicates (no rows deleted), and a flag column for the ambiguous names. Result: a clean 1,000 × 16 dataset.

### 2. EDA & SQL: understand the shape
Summary statistics, seven SQL business questions (including a multi-table join), a correlation matrix, and a dashboard mock-up. Key caveat caught early: the apparent January 2026 revenue "collapse" is only a partial month, not a real decline.

### 3. Deep dive: let the data change the question
A **5.5% repeat purchase rate** (52 of 947 customers) ruled out the planned retention analysis. The new question became: *if customers rarely return, which one-time customers matter most?* RFM segmentation answered it:

| Segment | Customers | Revenue | Share |
|---|---|---|---|
| High-Value One-Timer | 427 | ₹9.86 Cr | 70.7% |
| Low-Value One-Timer | 231 | ₹1.24 Cr | 8.9% |
| At Risk / Lapsed | 237 | ₹1.22 Cr | 8.7% |
| High-Value Loyal | 38 | ₹1.21 Cr | 8.7% |
| Repeat Buyer | 14 | ₹0.41 Cr | 2.9% |

![RFM segmentation](assets/rfm_segments_v2.png)

An interactive **Power BI dashboard** with a segment slicer lets any stakeholder isolate a segment and see its revenue, orders, and trend.

### 4. Validation & storytelling: prove it, then say it plainly
**H₀:** average order value of High-Value One-Timers equals everyone else's. **H₁:** it is greater.

| Result | Value |
|---|---|
| Test | Welch's two-sample t-test, one-tailed (Levene's test showed unequal variances) |
| t-statistic | 29.22 |
| p-value | < 0.0001 |
| 95% CI on the AOV gap | ₹1,49,024 – ₹1,70,492 per order |
| Cohen's d | 1.94 (large effect) |

**Business conclusion:** this is a retention problem, not a demand problem. Recommendation: a targeted win-back initiative for this exact segment instead of broad marketing, tracking repeat rate *within* the segment as the success metric.

---

## Key Learnings

1. **Don't invent data to make it tidy.** Where the truth was unknown (a missing city, a Customer ID with two names) I labelled or flagged it instead of guessing. The cost is a few `"Unknown"` rows; the benefit is that nothing downstream is built on a fabricated value.
2. **Let results redirect the question.** The 5.5% repeat rate killed my original plan (cohort retention analysis) and led to a better one. Knowing when *not* to run an analysis is part of the job.
3. **Check for caveats before reporting a number.** A –93.4% month-over-month "drop" turned out to be a partial month. Reporting it unqualified would have been wrong.
4. **Statistical significance is not the same as importance.** The p-value says the gap isn't chance; Cohen's d and the confidence interval say whether it's big enough to act on. I report all three.
5. **Make the result reproducible.** When my working environment reset, I rebuilt the entire cleaning and segmentation pipeline from the raw file and matched the earlier figures exactly (₹9.86 Cr for the top segment), which is the real test of whether the analysis is documented well enough.
6. **Lead with the answer.** The final deck opens with the conclusion, then shows how I reached it. Stakeholders need the "so what" first and the method second.

## Technical Skills Demonstrated

| Area | Skills |
|---|---|
| **Data wrangling** | Missing-value strategy, duplicate handling, data-quality profiling, feature engineering (Pandas) |
| **SQL** | Aggregation, grouping, multi-table `JOIN`, business-question framing (SQLite) |
| **Exploratory analysis** | Univariate stats, correlation analysis, skew and outlier assessment, Matplotlib / Seaborn |
| **Segmentation** | RFM scoring, business-rule segment design |
| **Statistics** | Hypothesis formulation, Levene's test, Welch's t-test, confidence intervals, Cohen's d |
| **BI & dashboards** | KPI definition, Power BI Desktop, slicer-driven interactive reports |
| **Communication** | Data storytelling (Objective → Analysis → Conclusions → Call to Action), stakeholder deck design, video walkthrough |

## Limitations (stated honestly)

- **One year of data.** The repeat-rate figure comes from a single-year window, so some "one-time" customers may simply not have reordered *yet*. The recommendation includes re-running the segmentation quarterly.
- **Partly circular test.** The High-Value One-Timer segment is defined partly by total spend, so a higher average order value is somewhat expected. To check the result wasn't an artefact of that definition, I also tested two variables **not** used to build the segments. Both differ significantly: Quantity (7.0 vs 4.3 units, t = 17.76, p < 0.0001) and Unit Price (₹33,892 vs ₹19,223, t = 19.63, p < 0.0001).
- **Association, not causation.** The analysis shows *where* revenue sits, not *why* these customers don't return. The proposed win-back campaign should be run as a test with a control group.

## Repository Layout

```
YourName-DataAnalyst-Internship-Portfolio/
├── README.md                  ← this page
├── index.html                 ← GitHub Pages site
├── deck/
│   └── ApexPlanet_Final_Presentation.pptx
├── docs/
│   ├── Task4_Data_Story.docx
│   ├── Task4_Hypothesis_Testing_Summary.docx
│   ├── Task4_Video_Script.md
│   └── Task5_Portfolio_Video_Script.md
└── assets/                    ← images used by README and site
```

Each task's code, data, and detailed write-up live in its own repository (linked in the table above).

## Tools

Python (Pandas, SciPy, Matplotlib, Seaborn), SQLite, Power BI Desktop, PowerPoint.

---

*Built during the ApexPlanet Data Analytics Internship. Questions and feedback welcome, so please connect with me on [LinkedIn](https://www.linkedin.com/in/YOUR-PROFILE).*
