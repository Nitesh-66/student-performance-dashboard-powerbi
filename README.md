# 📊 Students Performance Dashboard (Power BI)

##  Overview

This project is an interactive **Students Performance Dashboard** built using Power BI to analyze **academic performance, attendance, and behavior patterns**.

The dashboard provides a clear view of student insights through KPIs, charts, and filters, enabling better decision-making.

---

##  Key Features

*  KPI Cards:

  * Total Students: **1000**
  * Attendance %: **90.05%**
  * Average Score: **49.87**
  * Behavior Count: **6500**
  * Performance Category: **Low**

*  Performance Trend Analysis (by Term & Subject)

*  Subject-wise Average Score Comparison

*  Behavior Distribution Visualization

*  Detailed Student Performance Table with Conditional Formatting

*  Interactive Filters (Section, Term, Subject, Class)

---

##  Dataset Used

The dashboard is built using 4 datasets:

* **Students** → Student details (Name, Class, Section)
* **Scores** → Subject-wise marks and terms
* **Attendance** → Daily attendance (Present/Absent)
* **Behavior** → Student behavior records

---

##  Data Model

* One-to-Many Relationships:

  * Students → Scores
  * Students → Attendance
  * Students → Behavior

---

##  DAX Measures

### Total Score

```DAX id="m1a2b3"
Total Score = SUM(Scores[Score])
```

### Average Score

```DAX id="c4d5e6"
Average Score = AVERAGE(Scores[Score])
```

### Attendance %

```DAX id="f7g8h9"
Attendance % =
DIVIDE(
    CALCULATE(COUNT(Attendance[Status]), Attendance[Status] = "Present"),
    COUNT(Attendance[Status])
)
```

### Behavior Count

```DAX id="i1j2k3"
Behavior Count = COUNT(Behavior[BehaviorType])
```

### Performance Category

```DAX id="l4m5n6"
Performance Category =
SWITCH(
    TRUE(),
    [Average Score] >= 80, "High",
    [Average Score] >= 50, "Medium",
    "Low"
)
```

---

##  Dashboard Components

###  Performance Trend by Term

* Line chart showing subject-wise trends across terms (Term 1, 2, 3)

###  Average Score by Subject

* Stacked bar chart comparing subject performance across classes

###  Behavior Distribution

* Donut chart showing behavior categories:

  * Disruptive
  * Late
  * Helpful
  * Participative
  * Absent without notice

###  Student Performance Table

* Displays:

  * Student Name
  * Subject-wise scores
  * Total Score
* Includes conditional formatting:

  * 🔴 Low performance
  * 🟡 Medium
  * 🟢 High

---

##  Interactivity

* **Section Filter** (A, B, C)
* **Term Filter** (Term 1, Term 2, Term 3)
* **Subject Filter**
* **Class Range Slider (1–12)**
* **Reset Button** for quick dashboard reset

---

## 📈 Insights Generated

* Overall performance category is **Low**
* Attendance rate is high (**90%+**) but scores are moderate
* Certain subjects show declining trends across terms
* Behavior patterns highlight engagement and discipline issues
* Top-performing students identified using ranking logic

---

##  Tools & Technologies

* Power BI Desktop
* Power Query (Data Cleaning)
* DAX (Data Analysis Expressions)

---

##  File Included

* `Students_Performance_Dashboard.pbix`

---

##  How to Use

1. Open the `.pbix` file in Power BI Desktop
2. Use filters to explore data
3. Analyze trends using charts
4. Review student-level performance in table

---

##  Conclusion

This dashboard provides a **complete analytical view of student performance**, combining academic, attendance, and behavioral data into a single interactive report.

---

## 👤 Author

**Nitesh Kumar**
