# 🏏 Sachin Tendulkar Cricket Data Analysis (ODI & Test Matches)

## 📊 Project Overview
This Power BI project presents a **comprehensive analysis of Sachin Tendulkar’s ODI and Test Match career**, offering data-driven insights into his legendary performances.  
The dashboards visualize trends across runs, centuries, strike rates, and performances by year, ground, and opposition — providing a complete statistical view of the “Master Blaster’s” cricket journey.


---

## 🏆 Dashboards Included

### 🩵 **1. ODI Dashboard**
**Title:** `SACHIN TENDULKAR ODI DASHBOARD | Career at a Glance`  
**Description:**  
Analyzes Sachin Tendulkar’s One Day International (ODI) career through metrics such as runs, centuries, and ground-wise performance.  
This dashboard delivers an at-a-glance view of his dominance across opponents, years, and venues.

#### 📈 Key Highlights:
- Total Runs, Centuries, and Half-Centuries  
- Performance by Ground and Opposition  
- Yearly Runs and Centuries  
- Opposition-wise Runs and Milestones  

#### 🔧 DAX Measures Used:
```DAX
1st_inings = 
CALCULATE( COUNTROWS(sachin_odi),sachin_odi[batting_innings] = "1st")
ODI_Century = COUNTROWS(FILTER(sachin_odi, sachin_odi[C_batting_score] >= 100))

##  **2. Test Match Dashboard**
**Title:** `SACHIN TENDULKAR - Test Matches | Performance Overview`  
**Description:**  
Provides an in-depth view of Sachin Tendulkar’s Test career performance, focusing on consistency, longevity, and his dominance across venues and oppositions.  
It includes trends in runs, strike rates, centuries, and half-centuries over his entire Test career.

#### 📈 Key Highlights:
- Total Runs, Centuries, and Half-Centuries  
- Average Runs, Strike Rate, and Balls Faced  
- Performance by Year, Ground, and Opposition  
- Top 10 Grounds and Opponents by Runs
  
#### 🔧 DAX Measures Used:
```DAX
ave_ball_faced = AVERAGE(sachin_Test_batting[BF - numeric])
ave_Strike_Rate = AVERAGE(sachin_Test_batting[SR_Numeric])
ball_faced = SUMX(sachin_Test_batting, sachin_Test_batting[BF - numeric])
Century = CALCULATE(COUNT('sachin_Test_batting'[Runs - numeric]),FILTER(ALL(sachin_Test_batting[Runs - numeric]),sachin_Test_batting[Runs - numeric] >= 100))
Half_Century = COUNTROWS(FILTER(sachin_Test_batting,sachin_Test_batting[Runs - numeric] >= 50 &&sachin_Test_batting[Runs - numeric] < 100))
Total_matches = COUNTA(sachin_Test_batting[Match Number])
total_run = SUMX(sachin_Test_batting, sachin_Test_batting[Runs - numeric])

⚙️ Tools Used:

Power BI Desktop – Dashboard creation and visualization
Power Query – Data transformation and cleaning
DAX – Custom calculations and KPIs
Excel/CSV – Data source preparation

💡 Key Insights

Consistent run-scorer across both formats with 100 international centuries
Higher Test batting average (50+) compared to ODI (40+)
Excelled against Australia, England, and Sri Lanka
Dominated venues like Sharjah, Mumbai, and Sydney
Showcases his evolution from a young prodigy to a global cricket icon

🎯 Learning Outcomes

Built a multi-format Power BI analysis project
Learned to implement advanced DAX measures
Designed interactive and comparative visuals
Developed skills in data cleaning, modeling, and storytelling

🏁 Conclusion
This project serves as a data-driven tribute to Sachin Tendulkar, capturing his career milestones, records, and consistency across ODIs and Tests.
It demonstrates how data analytics and visualization can be used to celebrate and understand sports excellence.
“People throw stones at you and you convert them into milestones.” – Sachin Tendulkar

👨‍💻 Author
Gaurav Singh
Data Analyst | Power BI Developer | Cricket Analytics Enthusiast

📧 [gaurav36122@gmail.com]
🔗 [LinkedIn : - www.linkedin.com/in/gaurav-singh-692b24273]

