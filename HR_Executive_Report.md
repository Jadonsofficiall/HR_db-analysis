# HR Database Analysis: Executive Report

**Scope:** `hr\_db` schema (biodata, performance\_details, payroll\_details), 20 employees, 2025 performance reviews, September 2026 payroll.
**Source:** Eight DQL queries in the student project script.
**Report date:** 29 October 2026



\---

## 

## 1\. Executive summary

* **Payroll for September 2026 totals ₦6,553,000** across 20 employees. The average net pay is ₦327,650 and the median is ₦313,500.
* **Operations is the weakest department on every measure.** It has the lowest average pay (₦238,000, about 27% below the company average), the lowest average KPI (66.0), the lowest average training (9.5 hours) and no employee rated Exceeds or Outstanding.
* **Training and performance move together very closely** (KPI vs training hours, r = 0.96). The strongest performers averaged 23 to 32 training hours; the Meets and Below groups averaged 12 and 6.
* **Pay is only loosely linked to rating.** One employee rated Below (IT, ₦357,000) earns more than the Meets average and the Exceeds average.
* **The gender pay gap is 6.5% on the raw averages**, but this is driven by department mix. Within the two departments where both genders appear (Finance and Sales), the sample is too small to draw firm conclusions.

**Priority actions:** (1) review Operations' pay, development and performance plan; (2) check pay decisions for the Below-rated IT employee.

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/02_average_kpi_by_department.png)

\---



## 2\. Key metrics

|Metric|Value|
|-|-|
|Employees|20 (10 female, 10 male)|
|Departments|6|
|Total net pay, September 2026|₦6,553,000|
|Average / median net pay|₦327,650 / ₦313,500|
|Net pay range|₦211,000 to ₦578,000|
|Employees earning above ₦300,000 (Q5)|12 of 20 (60%)|
|Top three earners' share of payroll|23.2%|
|Allowances as share of gross pay|24.3%|
|Deductions as share of gross pay|9.6%|
|Average KPI score, 2025|76.6 (range 54 to 95)|
|Average training hours, 2025|16.9 (range 5 to 36)|
|Rating mix|2 Outstanding, 7 Exceeds, 8 Meets, 3 Below|



\---

## 

## 3\. Findings

### 3.1 Headcount is evenly split, with Sales and Operations the largest teams

Sales and Operations each have four employees. Finance, HR, IT and Marketing each have three. Gender is balanced at 10 and 10. HR and Marketing are all female; Operations and IT are all male.

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/05_gender_composition_by_department.png)



### 3.2 Finance pays the most, Operations pays the least

Average net pay by department (Q6):

|Department|Employees|Total net pay (₦)|Average net pay (₦)|Avg KPI|Avg training (hrs)|
|-|-|-|-|-|-|
|Finance|3|1,401,000|467,000|82.3|20.7|
|IT|3|1,213,000|404,333|78.3|19.7|
|Marketing|3|925,000|308,333|84.7|22.0|
|Sales|4|1,201,000|300,250|73.5|14.5|
|HR|3|861,000|287,000|79.3|18.3|
|Operations|4|952,000|238,000|66.0|9.5|

Marketing has the highest average KPI (84.7) yet sits in the middle for pay. Finance is the highest-paid department and also one of the strongest on performance. Operations has the lowest average KPI (66.0) and the lowest average training load (9.5 hours) of any department.

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/03_average_net_pay_by_department.png)



### 3.3 Training hours track performance closely

The ratings line up with training hours in a clear step pattern (Q8 and the rating breakdown):

|Rating|Employees|Avg KPI|Avg training (hrs)|Avg net pay (₦)|
|-|-|-|-|-|
|Outstanding|2|93.5|32.0|546,500|
|Exceeds|7|85.9|23.0|336,857|
|Meets|8|71.4|11.8|285,125|
|Below|3|57.7|6.3|273,667|

The correlation between KPI score and training hours is 0.96. This is very strong. It may reflect how the data was recorded rather than a causal link, so it should be treated as an association. The Exceeds group (7 employees) is the largest high-performing group and is the most useful target for development investment.

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/01_performance_rating_distribution.png)

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/04_training_vs_kpi.png)



### 3.4 Pay is only weakly linked to rating

Average pay rises with rating, but the spread within each rating is wide:

* Outstanding: ₦515,000 to ₦578,000.
* Exceeds: ₦298,000 to ₦425,000.
* Meets: ₦211,000 to ₦398,000.
* Below: ₦229,000 to ₦357,000.



The clearest mismatch is the IT employee rated Below (David Ifeanyi, KPI 61, 8 training hours), who earns ₦357,000. That is above the Meets average (₦285,125) and above the Exceeds average (₦336,857). Pay correlates moderately with training (0.69) and KPI (0.64), and the Below group's average (₦273,667) is close to the Meets group's average.

![](https://github.com/Jadonsofficiall/HR_db-analysis/blob/main/06_net_pay_distribution.png)



### 3.5 Gender pay gap is driven by department mix

* Average net pay for female employees is ₦316,600, against ₦338,700 for male employees. The raw gap is ₦22,100, or 6.5%.
* Six of the ten female employees are in HR and Marketing, the two lower-paid departments with no male staff. Operations and IT have no female staff.
* Within departments, the comparison is only possible in Finance and Sales. In Finance, the one male employee earns ₦578,000 against an average of ₦411,500 for two female employees. In Sales, male employees average ₦322,000 against ₦278,500 for female employees.

These within-department numbers rest on one to two people per group. They are not enough to support a conclusion about pay equity, but they should be checked with a larger dataset.



\---



## 4\. Risks

|Risk|Evidence|Severity|
|-|-|-|
|Operations underperformance and under-investment|Lowest pay, KPI and training; no top-rated staff|High|
|Pay not clearly tied to performance|Below-rated IT employee earns above the Meets and Exceeds averages|Medium|
|Possible gender pay gap|6.5% raw gap; within-department samples of 1 to 2|Medium|
|Concentration of pay in senior staff|Top three earners take 23.2% of payroll|Low|



\---



## 5\. Recommendations

1. **Operations review:** Look at pay bands, the reasons behind the low KPI and training figures, and whether the department has the resources it needs. Set a training target for Operations staff that is closer to the company average of 16.9 hours.
2. **Pay-for-performance check:** Review the pay decision for the IT employee rated Below. Confirm whether there is a documented reason, such as a role change, a retention agreement or a recording error.
3. **Targeted development for the Meets group:.** The Meets group averages 11.8 training hours against 23.0 for Exceeds. A development plan for the eight Meets employees is the most direct lever for moving people up a rating.
4. **Gender equity review:** Repeat the comparison across at least 12 months and all grades before drawing any conclusion. Include job grade, which this dataset does not record.

