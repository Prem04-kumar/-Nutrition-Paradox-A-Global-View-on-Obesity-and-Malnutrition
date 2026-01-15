# -Nutrition-Paradox-A-Global-View-on-Obesity-and-Malnutrition
A data-driven analysis of the global nutrition paradox, examining the coexistence of obesity and malnutrition across countries, age groups, and genders using SQL, Python, and data visualization techniques.

The objective is to derive actionable public health insights that can support policymakers, NGOs, and researchers in designing targeted nutrition interventions.

## 🌍 Domain

Global Health & Nutrition Analytics

Data Source: World Health Organization (WHO) – Global Health Observatory APIs

## 🎯 Business Problem

Despite economic progress, many countries experience rising obesity while still struggling with malnutrition. This project investigates:

How obesity and malnutrition vary across countries, regions, age groups, and genders

How trends have evolved from 2012 to 2022

Which regions and demographics require urgent intervention

## 🧠 Skills & Tools Used

# Python (Pandas, NumPy)

# ETL & Data Cleaning

# Feature Engineering

# Exploratory Data Analysis (EDA)

# SQL ( MySQL )

# Power BI 

# Data Visualization (Matplotlib, Seaborn, Plotly)

# pycountry (Country code conversion)

# 📊 Datasets Used Indicator API Endpoint Adult Obesity NCD_BMI_30C Child Obesity NCD_BMI_PLUS2C Adult Underweight NCD_BMI_18C Child Thinness NCD_BMI_MINUS2C

Each dataset contains country-level estimates by year, gender, and region, including confidence intervals.

# 🔄 Project Workflow WHO APIs ↓ Python (ETL + Cleaning + EDA) ↓ SQL Database (Obesity & Malnutrition Tables) ↓ Power BI / Streamlit Dashboards ↓ Insights & Policy Recommendations 🧹 Data Cleaning & Feature Engineering Columns Retained

* Year

* Gender

* Mean_Estimate

* LowerBound

* UpperBound

* Age_Group

* Country

* Region

* CI_Width

* Obesity_Level / Malnutrition_Level

* Column Renaming Original New TimeDim Year Dim1 Gender NumericValue Mean_Estimate Low LowerBound High UpperBound ParentLocation Region SpatialDim Country Country Code Conversion

* Converted ISO Alpha-3 country codes to full names using pycountry

* Handled special region codes like GLOBAL, AFR, SEAR, WB_LI, etc.

* New Features Created

* Age_Group: Adult / Child

* CI_Width: UpperBound - LowerBound

* Obesity_Level:

High (≥ 30)

Moderate (25–29.9)

Low (< 25)

* Malnutrition_Level:

High (≥ 20)

Moderate (10–19.9)

Low (< 10)

## 📈 Exploratory Data Analysis (EDA) EDA Objectives

Identify global and regional trends

Compare obesity vs malnutrition

Analyze gender and age-group disparities

Evaluate data reliability using CI_Width

Visualizations Used

Line plots (time trends)

Bar charts (top/bottom countries)

Box plots (regional variation)

Scatter plots (obesity vs malnutrition)

## 🗄️ SQL Database Design Tables Created

obesity

malnutrition

Each table stores cleaned and engineered data for efficient querying and dashboard integration.

Data Insertion

Database created using Python

Data inserted row-by-row using .iterrows()

## 🔢 SQL Query Analysis Obesity Queries (10)

Top regions by obesity (2022)

Highest obesity countries

India obesity trends

Gender-wise averages

CI-based reliability analysis

Age-group comparisons

Consistently low-obesity countries

Female vs male obesity gap

Global obesity trend

Malnutrition Queries (10)

Age-group averages

Most affected countries

Africa region trends

Gender disparity

CI-based reliability

Country-wise yearly change

Regions with lowest malnutrition

Increasing malnutrition detection

Year-wise min/max comparison

High-risk CI flags

## Combined Queries (5)

Obesity vs malnutrition comparison

Gender disparity analysis

Region-wise side-by-side comparison

Countries with obesity up & malnutrition down

Age-wise trend analysis

# 📊 Visualization & Dashboarding Power BI 

Interactive filters & slicers

Country & region-level drill-downs

Trend and comparison dashboards

Sample Visuals

Global trend lines

Map-based analysis

Stacked bar charts

Scatter plots


# 🔍 Key Insights

Obesity is rising rapidly in high-income regions

Child malnutrition remains high in parts of Africa and Asia

Gender disparities exist across regions

Some countries face a double burden of obesity and malnutrition

Data reliability varies significantly across regions

# 🩺 Recommendations

Prioritize double-burden countries for intervention

Focus on women and children in nutrition programs

Improve data quality in regions with high CI_Width

Design region-specific nutrition policies

# 📦 Final Deliverables

Cleaned Python DataFrames

SQL Database with 2 tables

25 SQL queries

EDA visualizations (7–12)

Power BI

Insight-driven recommendations

# 🚀 How to Run the Project

Clone the repository

Install required Python packages

Run ETL & EDA notebooks

Create SQL database and insert data

Connect Power BI

Explore dashboards and insights

# 📌 Conclusion

This project highlights the global nutrition paradox, where obesity and malnutrition coexist across countries and populations. Through data analysis and visualization, the study reveals significant regional, age-group, and gender-based disparities in nutritional outcomes. The findings emphasize that addressing global health challenges requires balanced, data-driven strategies that simultaneously target both undernutrition and overnutrition rather than treating them as separate issues.

# 👨‍💻 Author
Prem Kumar.A / Project Type: End-to-End Data Analytics / Portfolio Project
