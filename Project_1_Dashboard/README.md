# Excel Salary Dashboard

<img src="https://github.com/user-attachments/assets/17462f29-2f5f-4240-aa32-0bbd8877540a" width="1000" height="500"/>

## Introduction

This interactive salary insights dashboard was designed to assist professionals in evaluating compensation trends for data-related careers and ensuring fair pay based on the desired job title, the country, and the type of job they're looking for.

The data is from Luke Barousse Excel Course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](Project_1_Dashboard/1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Data Visualizarion**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

This dataset is based on real-world 2023 data science job listings, providing insights into:
- **👨‍💼 Job titles**
- **💰 Annual Salaries**
- **📍 Ragional Pay Variations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="https://github.com/user-attachments/assets/62b0dbe3-52b7-4596-8b74-d311876b8276" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Integrated a bar chart with formatted salary data, ensuring a clean and structured layout.
- 🎨 **Design Choice:** A horizontal graph simplifies salary comparison across job roles.
- 📉 **Data Organization:** Sorted job positions by descending salary for clearer insights
- 💡 **Insights Gained:** Senior and engineering roles consistenly offer higher pay than analyst positions.

#### 🗺️ Country Median Salaries - Map Chart

![03  Map chart GIF](https://github.com/user-attachments/assets/8c11b3c5-cf37-449d-9f1a-166d4d2d4124)

- 🛠️ **Excel Features:** Used the map chart function to display global salary differences.
- 🎨 **Design Choice:** A color-coded map provides instant regional salary visualization.
- 📊 **Data Representation:** Median salary values plotted for each availability country.
- 👁️ **Visual Enhancement:** Enables quick recognition of high-earning vs. low-earning locations
- 💡 **Insights Gained:** Helps identify global salary trends and regional pay gaps

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Filters results based on job title, location, work type and excludes missing salary values.
- 📊 **Array Formula:** An array fomula utilizing MEDIAN() and conditional IF statements.
- 🎯 **Tailored Insights:** Generated specific salary figures tailored to the chosen filters.
- **🔢 Formula Purpose:** The formula fills a summary table displaying salary insights.

🍽️ Background Table

![04  Median Salary Table](https://github.com/user-attachments/assets/fcc0eb30-06ef-4f0c-82c7-cd65cb8f8dab)

📉 Dashboard Implementation

<img src="https://github.com/user-attachments/assets/b67640b3-e6a8-437a-ba18-461fabe1ff4a" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** Removes duplicated, ignores entries with multiple job types, and filters out blank values.
- **🔢 Formula Purpose:** Creates a distinct list of work schedules to improve dashboard usability.

🍽️ Background Table

![06  Job Schedule Type Table](https://github.com/user-attachments/assets/eff48bd7-a48d-488c-9c8c-edd2799baa26)

📉 Dashboard Implementation:

<img src="https://github.com/user-attachments/assets/7f7a2bd3-3f1e-4b26-a898-fe6b5eca0560" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Applied validated lists for Job Title, Country, and Work Type using the Data Validation feature:
    - 🎯 User Benefits: Ensures structured and error-free selections.
    - 🚫 Prevent Mistakes: Blocks inconsistent or incorrect entries.
    - 👥 Dashboard Usability: Enhances user experience by streamlining data inputs.

<img src="https://github.com/user-attachments/assets/fd856c8e-a0af-485d-9dcb-4facf032459c" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

This dashboard provides a data-driven perspective on salary trends with data science careers. By leveraging real-world datasets and Excel's analytical tools, users can make informed career decisions based on salary, job type, andl location.
