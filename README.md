# 🏏 Sachin Tendulkar Cricket Data Analysis – Power BI Project

## 📊 Project Overview
**Sachin Tendulkar Cricket Data Analysis** is a Power BI project that showcases a detailed statistical exploration of the cricket legend’s **ODI and Test Match career**.  
The dashboards analyze his runs, centuries, averages, and performance against various opponents and grounds — providing a complete, data-driven view of the *Master Blaster’s* cricket journey.

---

## 📸 Dashboard Previews

### 🩵 ODI Dashboard
![ODI Dashboard](https://github.com/gaurav36122/sachin-tendulkar-cricket-analytics/blob/main/ODI%20DASHBOARD.png?raw=true)

### 🤍 Test Match Dashboard
![Test Match Dashboard](https://github.com/gaurav36122/sachin-tendulkar-cricket-analytics/blob/main/TEST%20MATCH%20DASHBOARD.png?raw=true)

---

## 🏆 Dashboards Overview

### 🩵 **1. ODI Dashboard**
**Title:** `SACHIN TENDULKAR ODI DASHBOARD | Career at a Glance`  
This dashboard visualizes Sachin’s ODI career with insights into **runs, centuries, and performances** by **year, opposition, and ground**.  
It highlights his journey across different stages of his ODI tenure.

#### 📈 Key Highlights
- Total Runs, Centuries, and Half-Centuries  
- Performance by Year, Ground, and Opposition  
- Top Grounds and Oppositions by Scores  
- Yearly Run & Century Trends  

#### 🔧 DAX Measures Used
```DAX
1st_inings = 
CALCULATE(
    COUNTROWS(sachin_odi),
    sachin_odi[batting_innings] = "1st"
)

ODI_Century = 
COUNTROWS(
    FILTER(sachin_odi, sachin_odi[C_batting_score] >= 100)
)
```

---

### 🤍 **2. Test Match Dashboard**
**Title:** `SACHIN TENDULKAR - Test Matches | Performance Overview`  
Analyzes Sachin’s **Test Match performance** through key metrics such as runs, centuries, averages, strike rates, and consistency across years and opponents.

#### 📈 Key Highlights
- Total Runs, Centuries, Half-Centuries, and Matches  
- Yearly Runs & Centuries  
- Performance by Opposition and Ground  
- Average Balls Faced and Strike Rate  

#### 🔧 DAX Measures Used
```DAX
ave_ball_faced = 
AVERAGE(sachin_Test_batting[BF - numeric])

ave_Strike_Rate = 
AVERAGE(sachin_Test_batting[SR_Numeric])

ball_faced = 
SUMX(sachin_Test_batting, sachin_Test_batting[BF - numeric])

Century = 
CALCULATE(
    COUNT('sachin_Test_batting'[Runs - numeric]),
    FILTER(
        ALL(sachin_Test_batting[Runs - numeric]),
        sachin_Test_batting[Runs - numeric] >= 100
    )
)

Half_Century = 
COUNTROWS(
    FILTER(
        sachin_Test_batting,
        sachin_Test_batting[Runs - numeric] >= 50 &&
        sachin_Test_batting[Runs - numeric] < 100
    )
)

Total_matches = 
COUNTA(sachin_Test_batting[Match Number])

total_run = 
SUMX(sachin_Test_batting, sachin_Test_batting[Runs - numeric])
```

---

## 🗂 Dataset

### 📁 Data Files
- `sachin_odi.csv` – ODI career data (match-by-match stats)  
- `sachin_test.csv` – Test career data (batting performance)  

### 📊 Dataset Columns
Common columns used for both datasets include:
- **Match Date** – Match date  
- **Opponent** – Opposition team  
- **Ground** – Match venue  
- **Runs** – Runs scored  
- **Balls Faced** – Deliveries faced  
- **Strike Rate** – Batting strike rate  
- **Batting Innings** – 1st or 2nd innings indicator  
- **Result** – Match outcome (Win/Loss/Draw)  

---

## 🧹 Data Cleaning & Transformation
Performed in **Power Query Editor** to ensure clean and accurate data:
- Removed **nulls**, **duplicates**, and **invalid records**  
- Converted string-based numbers to numeric format  
- Added new columns for **match year** and **opposition category**  
- Built DAX measures for dynamic insights (runs, averages, centuries)

---

## 📊 Dashboard Features
Interactive Power BI visuals include:
- **Cards** – Total Runs, Centuries, Half-Centuries, Strike Rate  
- **Bar Charts** – Runs & Centuries by Opposition and Ground  
- **Line Charts** – Yearly performance trends  
- **Tables** – Detailed performance summaries  
- **Slicers** – Filter by Year, Opposition, or Ground  

---

## 🎯 Objectives
- Provide a **data-driven tribute** to Sachin Tendulkar’s cricket legacy  
- Showcase **performance insights** across ODI and Test formats  
- Practice **advanced DAX** and **Power BI visualization** techniques  
- Demonstrate **data storytelling** through interactive dashboards  

---

## ⚡ Tools & Technologies
- **Power BI Desktop** – Dashboard design & modeling  
- **Power Query** – Data transformation  
- **DAX (Data Analysis Expressions)** – Calculations & KPIs  
- **Excel/CSV** – Data source preparation  

---

## 🔗 Repository Structure
```
Sachin-Tendulkar-Cricket-Analysis/
│
├─ Dataset/
│   ├─ sachin_odi.csv
│   └─ sachin_test.csv
│
├─ PowerBI/
│   └─ Sachin_Tendulkar_Career.pbix
│
├─ ODI DASHBOARD.png
├─ TEST MATCH DASHBOARD.png
└─ README.md
```

---

## ✅ Conclusion
The **Sachin Tendulkar Cricket Data Analysis** project demonstrates how **data analytics and visualization** can bring sports statistics to life.  
It highlights Tendulkar’s consistency, dominance, and legendary achievements across both ODI and Test formats.

> *“People throw stones at you and you convert them into milestones.”* – **Sachin Tendulkar**

---

## 🏷 Hashtags
#PowerBI #CricketAnalytics #SachinTendulkar #DataVisualization #SportsAnalytics #DAX #BusinessIntelligence  

---

👤 **Author**
**Gaurav Singh**  
📧 Email: (gaurav36122@gmail.com)  
💼 LinkedIn:(https://www.linkedin.com/in/gaurav-singh-692b24273)  
