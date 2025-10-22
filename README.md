# HR Attrition Analysis (Part 2): Hypothesis Testing

This project is a follow-up analysis to my [End-to-End HR Attrition EDA (Part 1)](PASTE-LINK-TO-YOUR-FIRST-GITHUB-REPO-HERE).

The initial EDA (Part 1) revealed a counter-intuitive insight: the company was losing high-performing employees who had *more* training and *higher* manager ratings.

### Project Objective

The goal of this "Part 2" analysis was to test the hypothesis from Part 1: **"Are high-performers leaving due to wage and promotion stagnation?"**

---

### Methodology

1.  **Segmentation:** I isolated a cohort of 610 "High-Performers" (defined as employees with a Manager Rating of 4 or 5).
2.  **Analysis:** I split this cohort into two groups: "Stayed" (0) and "Left" (1).
3.  **Hypothesis Test:** I compared the `Salary` and `YearsSinceLastPromotion` for these two groups, using T-tests to verify statistical significance.

**Tech Stack:** Python, pandas, seaborn, and **SciPy** (for statistical T-tests).

---

### Key Findings & The "Twist"

My hypothesis was only half-right. The results revealed a specific and actionable "twist":

#### Finding 1: We are losing our UNDERPAID High-Performers.
The data was conclusive. High-performers who **left** earned significantly less than those who stayed.
* **Avg. Salary (Stayed):** $120,237
* **Avg. Salary (Left):** $86,956
* **Result:** The $33k difference is statistically significant (p < 0.05).

![Salary Distribution for High-Performers](hp_salary_vs_attrition_boxplot.png)

#### Finding 2: We are losing our RECENTLY PROMOTED High-Performers.
This finding contradicted my initial hypothesis. The employees who left were being promoted *more* frequently.
* **Avg. Years Since Promotion (Stayed):** 4.54 years
* **Avg. Years Since Promotion (Left):** 1.68 years
* **Result:** This difference is also highly significant (p < 0.001).

![Promotion Timing for High-Performers](hp_promo_vs_attrition_boxplot.png)

---

### Actionable Conclusion

**The problem is not a lack of promotion; it's that our promotions are not funded correctly.**

The data tells a clear story:
1.  An employee performs well and is identified as a high-performer.
2.  They are **promoted** (at ~1.7 years).
3.  However, their **salary is not adjusted** to a competitive level, remaining at a low ~$87k.
4.  This newly-promoted, high-potential employee now has a new title and proven skills, so they take that title to the external market to get the significant pay raise we failed to give them.

We are successfully retaining our "comfortably stagnant" high-performers (high pay, few promotions) but losing our "ambitious and underpaid" ones.
