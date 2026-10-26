# Task 4 — LinkedIn Stakeholder Video Script

**Target length:** ~9 minutes (about 1,250 spoken words at a calm pace of ~140 words/min)
**How to record:** Screen-share the deck `ApexPlanet_Final_Presentation.pptx` and talk over it. Move to the next slide where you see **[NEXT SLIDE]**.
**Tone:** Speak to the stakeholder (a business owner), not to a teacher. Lead with business impact; keep the statistics light.

---

## Slide 1 — Title (0:00 – 0:30)

Hello, everyone. My name is [YOUR NAME], and I'm a Data Analytics intern at ApexPlanet.

Over the last four tasks, I took a raw sales dataset and turned it into a specific, statistically validated business recommendation. In the next nine minutes, I'll walk you through that journey, and end with what I think ApexPlanet should do next.

**[NEXT SLIDE]**

## Slide 2 — Executive Summary (0:30 – 1:30)

Let me start with the answer, and then show you how I got there.

**Seventy-one percent of ApexPlanet's revenue comes from just 427 customers, which is 45 percent of the customer base. And every one of them bought only once.**

That is the whole story in one sentence. Everything else in this presentation is how I found it, why you can trust it, and what to do about it.

There are four steps: I started with raw data and cleaned it. I found a concentration pattern. I proved it statistically, so it isn't a fluke. And I'm recommending one specific action.

**[NEXT SLIDE]**

## Slide 3 — The Starting Point (1:30 – 2:30)

The objective: ApexPlanet had one year of sales data, 1,000 orders from 947 unique customers, totalling about 13.94 crore rupees in revenue. But nobody had analysed it. My goal was to find out where the revenue comes from and what to do about it.

Before any analysis, the data needed work. Twenty rows had a missing age, and I filled those with the median. Thirteen had a missing city, and I labelled those "Unknown" rather than guess. Nine orders shared one duplicate Order ID, so I gave them new IDs and lost no data. And 52 Customer IDs were linked to more than one name. I flagged those instead of guessing which name was right.

The principle was simple: never invent data to make the analysis look cleaner.

**[NEXT SLIDE]**

## Slide 4 — The Analysis Journey (2:30 – 3:30)

The work happened in four stages, each building on the last.

Step one, **Clean and Structure**: one reliable, analysis-ready dataset.

Step two, **Explore and Query**: summary statistics, SQL business questions, and correlation analysis. This showed that revenue was right-skewed, meaning a few big orders mattered a lot.

Step three, **Define KPIs and Segment**. This is where the project changed direction, and I'll explain why on the next slide.

Step four, **Validate and Tell the Story**: a hypothesis test to confirm the finding, and this presentation.

**[NEXT SLIDE]**

## Slide 5 — Core KPIs and the Turning Point (3:30 – 4:45)

Three core KPIs. Average Order Value is ₹1,39,399. Revenue per Customer is ₹1,47,201. And Repeat Purchase Rate is **5.5 percent**.

That last number reframed the whole project. Only 52 of 947 customers ever placed a second order.

I had planned to do a cohort or retention analysis. But with so few returning customers, there was nothing meaningful to study. So I asked a different question: *if customers mostly don't come back, which one-time customers matter most?*

That question led directly to segmenting customers by Recency, Frequency, and Monetary value, which is called RFM.

**[NEXT SLIDE]**

## Slide 6 — The Big Finding (4:45 – 6:00)

Here is what the RFM segmentation showed.

The orange bar is the **High-Value One-Timer** segment: customers who placed a single large order and never returned. They generated about **9.86 crore rupees**.

Now look at the others. At Risk customers: 1.22 crore. Low-Value One-Timers: 1.24 crore. High-Value Loyal customers: 1.21 crore. Repeat Buyers: 0.41 crore.

So this one segment of 427 customers produced more revenue than **every repeat and loyal customer combined**. That is 71 percent of total revenue.

The loyal customers, the ones most businesses focus on, are a very small part of the picture here.

**[NEXT SLIDE]**

## Slide 7 — Statistical Validation (6:00 – 7:30)

A good analyst should be suspicious of a result like that. Could this just be chance? So I tested it.

The null hypothesis says the average order value of High-Value One-Timers is the same as everyone else's. The alternative says it's greater.

I used Welch's t-test, because the two groups have unequal variance. The results: a **t-statistic of 29.22** and a **p-value below 0.0001**, far below the usual 0.05 threshold. The 95 percent confidence interval says High-Value One-Timers spend between roughly **₹1.49 lakh and ₹1.70 lakh more per order**. And the effect size, Cohen's d, is **1.94**. Anything above 0.8 is considered large.

So the null hypothesis is rejected. The gap is statistically significant, and it's large enough to matter in practice, not just significant on paper.

> *Optional line — only use if you're comfortable explaining it:* "One more check: since this segment is partly defined by spend, I also tested Quantity and Unit Price, which were not used to build the segments, and both also differed significantly."

**[NEXT SLIDE]**

## Slide 8 — Business Conclusions (7:30 – 8:30)

Three conclusions.

**One: revenue is concentrated, not distributed.** A defined, identifiable 45 percent of customers drive 71 percent of revenue, and we've shown that's not chance.

**Two: this is a retention problem, not a demand problem.** These customers have already shown they'll spend well above the typical order. They simply aren't coming back to do it again.

**Three: generic marketing is not the highest-leverage option.** This segment is specific enough to target directly, instead of running broad campaigns aimed at everyone.

**[NEXT SLIDE]**

## Slide 9 — Call to Action (8:30 – 9:15)

So what should ApexPlanet do?

**First, launch a targeted win-back initiative** aimed at High-Value One-Timers, for example a time-limited second-purchase incentive sent shortly after their first order.

**Second, track the repeat rate within this segment** as the key success metric, not just the overall repeat rate.

**Third, treat the dashboard as a living source of truth.** It updates as new orders arrive, and anyone can filter it to this segment.

**Fourth, re-run the segmentation quarterly.** The current repeat-rate figure is based on a single year of data, so it should be refreshed.

Thank you for watching. I'd welcome your questions and feedback in the comments.

---

## Recording tips

- **Practise once out loud first.** Reading cold sounds flat; reading the second time sounds natural.
- **Say the big numbers slowly:** 71 percent, 427 customers, 5.5 percent, 29.22.
- **Don't read slide text word for word.** The script adds context the slide doesn't show.
- **Run long or short?** If you're over 10 minutes, trim Slide 4 (it just previews other slides). If you're under 7, slow down on Slides 6 and 7.
- **Upload on LinkedIn** as a native video (not a YouTube link), with the GitHub repo link in the post.
