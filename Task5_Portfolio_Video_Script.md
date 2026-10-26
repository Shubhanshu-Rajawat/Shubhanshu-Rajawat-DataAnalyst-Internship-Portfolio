# Task 5 — Portfolio Walkthrough & Learning Reflections (Video Script)

**Target length:** ~4 minutes 30 seconds (about 620 spoken words at ~140 words/min). The brief asks for 3–5 minutes.
**What's on screen:** Your portfolio website first, then the GitHub README, one task repository, and two slides from the deck.
**Before you record:** open these tabs in order — (1) portfolio site, (2) master README on GitHub, (3) one task repo, (4) the deck on slides 6 and 7. Replace every `[bracket]` below.

---

## 0:00 – 0:25 | Opening — on the portfolio site

Hi, I'm [YOUR NAME]. I just finished a Data Analytics internship at ApexPlanet, and this is my portfolio, which brings all four tasks together in one place.

In the next four minutes, I'll show you what I built, what I found, and what I learned. The short version: I took a messy sales dataset and turned it into a recommendation I could actually prove.

## 0:25 – 1:10 | The hero — click the Customers / Revenue toggle

Let me start with the picture at the top of the page. Each dot is one customer, 947 in total. The orange ones are what I call High-Value One-Timers: customers who bought exactly once, and spent a lot.

That's 427 customers, 45 percent of the base. Now watch what happens when I switch to Revenue. The orange dots take over, because those same customers produced 9.86 crore rupees out of 13.94 crore, which is 71 percent of all revenue.

That one insight is the thread running through the whole internship.

## 1:10 – 2:30 | The four tasks — scroll to the task list

Each task answered the question the previous one raised.

**Task 1, Data Wrangling.** Can I trust this data? There were missing ages and cities, duplicate order IDs, and 52 customer IDs linked to more than one name. I fixed what I safely could, and I flagged the rest instead of guessing.

**Task 2, Exploration and SQL.** What does the data look like? I answered seven business questions in SQL and found that revenue is right-skewed: a few big orders pull the average up.

**Task 3, Deep Dive and Dashboard.** Where does revenue come from? Only 5.5 percent of customers ever ordered twice, so retention analysis was pointless. That changed my question, and I used RFM segmentation instead. That's where the 71 percent finding appeared, and I built an interactive Power BI dashboard so anyone can explore it.

**Task 4, Storytelling and Validation.** Is it real? I ran a Welch's t-test. The result was highly significant, with an effect size of 1.94, which is very large. So my recommendation is a targeted win-back campaign for this one segment.

## 2:30 – 3:00 | The deck and repos — switch to GitHub, then slides 6 and 7

Every task has its own repository with code, data, and a README. And here is the final presentation. It opens with the answer, then shows the evidence: the revenue chart on slide 6, and the statistical proof on slide 7.

## 3:00 – 4:10 | What I learned — back to the camera or the "What I learned" section

Three lessons I'll carry forward.

First, **don't invent data to make it tidy.** When I didn't know a customer's city or which name was correct, I labelled it or flagged it. A few "Unknown" rows are better than numbers built on a guess.

Second, **let the results change your question.** My plan was a retention analysis. The data said that wouldn't work, and the better question turned out to be more valuable.

Third, **be honest about limits.** My test was partly circular, because the segment is defined by spend, so I checked quantity and unit price too, which weren't used to build it. Both still differed significantly. And it's only one year of data, so the next step should be a controlled test, not a leap of faith.

## 4:10 – 4:30 | Close

If you'd like to dig in, the portfolio site and the full GitHub repository are linked below this video. I'd love your feedback, and if you're hiring for data roles, I'd be glad to talk. Thank you for watching.

---

## Recording tips

- **Do one silent run-through** to rehearse the clicks, especially the Customers / Revenue toggle at 0:45. It's your best 10 seconds on screen.
- **Slow down on numbers:** 427, 45 percent, 71 percent, 1.94.
- **Too long?** Trim the Task 1 and Task 2 lines in the task section. **Too short?** Spend longer on the toggle and on slide 7.
- **Upload natively to LinkedIn** (not as a YouTube link) and put the portfolio link in the first comment as well as the post.
