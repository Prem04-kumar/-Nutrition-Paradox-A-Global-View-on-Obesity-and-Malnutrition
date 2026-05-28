# 🌍 Nutrition Paradox: A Global View on Obesity and Malnutrition
 
![Python](https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![WHO](https://img.shields.io/badge/Data%20Source-WHO-0093D5?style=for-the-badge&logo=data:image/png;base64,&logoColor=white)
 
---
 
## 📌 Project Overview
 
A data-driven analysis of the **global nutrition paradox** — the coexistence of obesity and malnutrition across countries, age groups, and genders — using SQL, Python, and advanced data visualization techniques.
 
> The objective is to derive **actionable public health insights** that can support policymakers, NGOs, and researchers in designing targeted nutrition interventions.
 
---
 
## 🌐 Domain
 
**Global Health & Nutrition Analytics**
 
**Data Source:** World Health Organization (WHO) — Global Health Observatory APIs
 
---
 
## 🎯 Business Problem
 
Despite economic progress, many countries experience **rising obesity** while still struggling with **malnutrition**. This project investigates:
 
| Research Question | Description |
|-------------------|-------------|
| 🌎 Geographic Variation | How obesity and malnutrition differ across countries and regions |
| 👶 Demographic Disparities | How age groups and genders are affected differently |
| 📅 Temporal Trends | How patterns have evolved from **2012 to 2022** |
| 🚨 Urgent Interventions | Which regions and demographics need immediate attention |
 
---
 
## 🛠️ Skills & Tools Used
 
| Category | Tools |
|----------|-------|
| Programming | Python (Pandas, NumPy) |
| Database | SQL (MySQL) |
| Visualization | Matplotlib, Seaborn, Plotly |
| BI Dashboard | Power BI |
| Data Access | WHO GHO APIs |
| Utilities | pycountry (country code conversion) |
| Environment | Jupyter Notebook |
 
---
 
## 📊 Datasets Used
 
Data fetched directly from **WHO Global Health Observatory APIs**:
 
| Indicator | API Endpoint |
|-----------|--------------|
| Adult Obesity | `NCD_BMI_30C` |
| Child Obesity | `NCD_BMI_PLUS2C` |
| Adult Underweight | `NCD_BMI_18C` |
| Child Thinness | `NCD_BMI_MINUS2C` |
 
> Each dataset contains **country-level estimates** by year, gender, and region, including confidence intervals.
 
---
 
## 🔄 Project Workflow
 
```
WHO APIs
    ↓
Python (ETL + Cleaning + EDA)
    ↓
SQL Database (Obesity & Malnutrition Tables)
    ↓
Power BI Dashboards
    ↓
Insights & Policy Recommendations
```
 
---
 
## 🧹 Data Cleaning & Feature Engineering
 
### Column Renaming
 
| Original | Renamed To |
|----------|------------|
| `TimeDim` | `Year` |
| `Dim1` | `Gender` |
| `NumericValue` | `Mean_Estimate` |
| `Low` | `LowerBound` |
| `High` | `UpperBound` |
| `ParentLocation` | `Region` |
| `SpatialDim` | `Country` |
 
### Columns Retained
 
- `Year`, `Gender`, `Mean_Estimate`, `LowerBound`, `UpperBound`
- `Age_Group`, `Country`, `Region`, `CI_Width`
- `Obesity_Level` / `Malnutrition_Level`
### Country Code Conversion
 
- Converted **ISO Alpha-3** country codes to full names using `pycountry`
- Handled special region codes: `GLOBAL`, `AFR`, `SEAR`, `WB_LI`, etc.
### New Features Created
 
| Feature | Description |
|---------|-------------|
| `Age_Group` | Adult / Child |
| `CI_Width` | `UpperBound - LowerBound` (data reliability indicator) |
| `Obesity_Level` | High (≥ 30) / Moderate (25–29.9) / Low (< 25) |
| `Malnutrition_Level` | High (≥ 20) / Moderate (10–19.9) / Low (< 10) |
 
---
 
## 📈 Exploratory Data Analysis (EDA)
 
### EDA Objectives
 
- Identify global and regional nutrition trends
- Compare obesity vs. malnutrition rates
- Analyze gender and age-group disparities
- Evaluate data reliability using `CI_Width`
### Visualizations Used
 
- 📈 Line plots — time-series trends
- 📊 Bar charts — top/bottom countries
- 📦 Box plots — regional variation
- 🔵 Scatter plots — obesity vs. malnutrition correlation
---
 
## 🗄️ SQL Database Design
 
### Tables Created
 
| Table | Description |
|-------|-------------|
| `obesity` | Cleaned obesity data with engineered features |
| `malnutrition` | Cleaned malnutrition data with engineered features |
 
> Data inserted row-by-row using Python's `.iterrows()` into a MySQL database.
 
---
 
## 🔢 SQL Query Analysis
 
### Obesity Queries (10)
 
1. Top regions by obesity (2022)
2. Highest obesity countries
3. India obesity trends
4. Gender-wise averages
5. CI-based reliability analysis
6. Age-group comparisons
7. Consistently low-obesity countries
8. Female vs. male obesity gap
9. Global obesity trend over time
10. Year-wise obesity growth rate
### Malnutrition Queries (10)
 
1. Age-group averages
2. Most affected countries
3. Africa region trends
4. Gender disparity analysis
5. CI-based reliability flags
6. Country-wise yearly change
7. Regions with lowest malnutrition
8. Increasing malnutrition detection
9. Year-wise min/max comparison
10. High-risk CI flagging
### Combined Queries (5)
 
1. Obesity vs. malnutrition comparison
2. Gender disparity analysis
3. Region-wise side-by-side comparison
4. Countries with obesity rising & malnutrition falling
5. Age-wise trend analysis
---
 
## 📊 Power BI Dashboard
 
Features:
- 🔲 Interactive filters & slicers
- 🌍 Country & region-level drill-downs
- 📅 Trend and comparison dashboards
### Visuals Included
 
- Global trend lines
- Map-based country analysis
- Stacked bar charts
- Scatter plots (double-burden analysis)
---
 
## 🔍 Key Insights
 
- 📈 **Obesity is rising rapidly** in high-income and middle-income regions
- 🌍 **Child malnutrition remains high** in parts of Africa and South/Southeast Asia
- ♀️ **Gender disparities** exist — female obesity rates are higher in several regions
- ⚖️ Some countries face a **double burden** — rising obesity alongside persistent malnutrition
- 📉 **Data reliability varies** significantly; CI_Width is wider in low-income regions
---
 
## 🩺 Policy Recommendations
 
| Priority | Recommendation |
|----------|---------------|
| 🎯 Double-burden countries | Design simultaneous obesity & undernutrition programs |
| 👩‍👧 Vulnerable groups | Focus nutrition programs on women and children |
| 📊 Data quality | Invest in improving surveillance in high CI_Width regions |
| 🏛️ Policy design | Develop region-specific, culturally relevant nutrition strategies |
 
---
 
## 📦 Final Deliverables
 
- ✅ Cleaned Python DataFrames (ETL pipeline)
- ✅ SQL Database with 2 structured tables
- ✅ 25 SQL queries (Obesity + Malnutrition + Combined)
- ✅ EDA visualizations (7–12 charts)
- ✅ Power BI interactive dashboard (`.pbix`)
- ✅ Insight-driven policy recommendations
---
 
## 📁 Project Structure
 
```
Nutrition-Paradox/
│
├── Nutrition_project.ipynb    # Main notebook — ETL, EDA, SQL, Analysis
├── nutrition.bi.pbix          # Power BI dashboard file
└── README.md                  # Project documentation
```
 
---
 
## 🚀 How to Run the Project
 
### 1. Clone the Repository
 
```bash
git clone https://github.com/Prem04-kumar/-Nutrition-Paradox-A-Global-View-on-Obesity-and-Malnutrition.git
```
 
### 2. Install Required Python Packages
 
```bash
pip install pandas numpy matplotlib seaborn plotly pycountry requests sqlalchemy pymysql jupyter
```
 
### 3. Run the Notebook
 
```bash
jupyter notebook Nutrition_project.ipynb
```
 
### 4. Set Up SQL Database
 
- Create a MySQL database
- Run the data insertion cells in the notebook to populate `obesity` and `malnutrition` tables
### 5. Open Power BI Dashboard
 
- Open `nutrition.bi.pbix` in **Power BI Desktop**
- Connect to your local MySQL database
- Explore interactive dashboards and insights
---
 
## 🌐 Future Enhancements
 
- [ ] 🚀 Deploy as a **Streamlit web app** for public access
- [ ] 🔮 Add **predictive modeling** for future obesity/malnutrition trends
- [ ] 🌍 Integrate **socioeconomic indicators** (GDP, HDI, food security index)
- [ ] 📡 Build a **real-time WHO API pipeline** for live data refresh
- [ ] 🤖 Apply **clustering** to group countries by nutritional risk profiles
- [ ] 📊 Expand dashboard with **drill-through reports** per country
---
 
## 📌 Conclusion
 
This project highlights the **global nutrition paradox**, where obesity and malnutrition coexist across countries and populations. Through data analysis and visualization, the study reveals significant regional, age-group, and gender-based disparities in nutritional outcomes.
 
| Pillar | Contribution |
|--------|-------------|
| 🔬 Data Analysis | ETL, feature engineering, and EDA using Python |
| 🗄️ SQL Analytics | 25 structured queries for business-ready insights |
| 📊 Visualization | Matplotlib, Seaborn, Plotly, and Power BI |
| 💡 Policy Impact | Actionable recommendations for global health stakeholders |
 
> The findings emphasize that addressing global health challenges requires **balanced, data-driven strategies** that simultaneously target both undernutrition and overnutrition — rather than treating them as separate issues.
 
---
 
## 👨‍💻 Author
 
**Prem Kumar A**
 
[![GitHub](https://img.shields.io/badge/GitHub-Prem04--kumar-181717?style=for-the-badge&logo=github)](https://github.com/Prem04-kumar)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/)
 
> 📁 Project Type: **End-to-End Data Analytics Portfolio Project**
 
---
 
> ⭐ **If you found this project helpful, please give it a star on GitHub!**
