
# Project 2 Analysis

## Introduction

As someone looking to get into the data field, i needed comprehensive data of the most valuable skills and job opportunities in the data science field. This project aims to identify key employer demands and strategies to maximize earnings

### Questions to Analyze

To gain deeper insights into the data science job market, I investigated

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

This analysis is based on 2023 real-world job listings, providing insights into:

- **👨‍💼 Job Positions**
- **💰 Salary Trends**
- **📍 Regional Differences**
- **🛠️ Key Technical Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Tools Used: Power Query (ETL)

#### 📥 Data Extraction

- Imported job data (`data_salary_all.xlsx`) and created two queries:
    - 🗃️ One containing complete job listings.
    - 🔧 Another mapping skills to job IDs.

#### 🔄 Data Transformation

- Standarized column formats, removed unnecessary fields, and refined text entries
    - 📊 data_jobs_all

      ![01 data_jobs_all_steps](https://github.com/user-attachments/assets/76c44350-e252-45e3-ac13-75bed919c57f)

    - 🛠️ data_job_skills

      ![02 data_jobs_skills_steps](https://github.com/user-attachments/assets/bd990299-a2a9-479e-983d-873de611242b)

#### 🔗 Data Load

- Loaded both refined queries into Excel for structured analysis.

    - 📊 data_jobs_all

        ![03 data_jobs_all_table](https://github.com/user-attachments/assets/2060b742-c866-44b0-b13b-e358fe55e654)

    - 🛠️ data_job_skills

        ![04 data_jobs_skills_table](https://github.com/user-attachments/assets/17fa4905-6870-4d29-8597-0c55cdd1d4ab)

### 📊 Analysis

#### 💡 Insights

- 📈 Job postings requiring more skills tend to offer higher median salaries, especially for Senior Data Engineers and Data Scientists.
- 💼 Positions demanding fewer skills, such as Business Analysts, tend to have lower salaries.

    ![05 Salary_VS_Skills_Scatter_Plot](https://github.com/user-attachments/assets/f4698ddd-2d09-49d2-8bc9-9759b1d2e542)

#### 🤔 Conclusion:

- Expanding technical expertise, espcially in high-demand fields, can significantly boost salary potential.
- 
## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 Developed a PivotTable based on the Data Model built with Power Pivot.
- 📊 Plotted `job_title_short`(rows) against `salary_year_avg` (values).
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Rolesl like Senior Data Engineer and Data Scientist consistenly command higher median salaries both in the US and internationally
- 💰 Salary gaps between US and Non-US roles are notable in tech jobs, likely influenced by industry concentration

    ![06 salary_analysis_page](https://github.com/user-attachments/assets/d9689b1d-4170-45fa-aa61-e5c518236f9c)

#### **🤔 Conclusion**

- These insights aid in salary negotiation and career planning, ensuring alignment with market trends.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Tool Used: Power Pivot

#### 💪 Power Pivot

- 🔗 Integrated `data_jobs_all` and `data_jobs_skills` into a single relational model
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    ![07 data_model_relationship](https://github.com/user-attachments/assets/0b2cf54a-114d-444e-bbc8-c940d8bbc2b6)

#### 📃 Power Pivot Menu

- Refined data relationships using Power Pivot tools for more efficient querying.

    ![08 power_pivtot_table](https://github.com/user-attachments/assets/27be64e8-a997-468e-b8d4-c5d4b6d64bed)

### 📊Analysis

#### 💡Insights

- 💻 SQL and Python remain the top skills in data-related roles.
- ☁️ The rise of AWS & Azure signals a shift towards cloud computing and big data.

    ![09 skill_job_analysis_graph](https://github.com/user-attachments/assets/01b1c53b-4575-40ce-8bdc-e68d7140bd0c)

#### 🤔Conclusion

- Knowing which skills are in high demand helps professionals stay competitive and training programs prioritize relevant technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Tools Used: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Python, Oracle and SQL command the highest salaries, proving their value in tech careers.
- 📉 PowerPoint and Word rank the lowest, indicating their limited impact on high-paying roles.

    ![10 skill_salary_analysis_graph](https://github.com/user-attachments/assets/1dd34b8e-e5a5-4806-b0e2-188f6a96983b)

### 🤔Conclusion:

- Investing in high-value skills like Python & SQL is essential for maximizing earning potential in tech careers.

## Conclusion

This project provided actionable insights into the data science job market, revealing key salary trends, regional differences, and essential skills.

By utilizing Excel's advanced features, such as PowerQuery, PivotTables, and DAX, this analysis offers valuable guidance for job seekers and professionals looking to boost their salaries and career prospects.
