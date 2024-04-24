## HR-Analytics in Power BI

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Data Visualization](#data-visualization)
- [Functions Used](#functions-used)
- [Results and Findings](#results-and-findings)
- [Recomendations](#recomendations)


### Project Overview
Purpose of the project is to develop a dynamic and interactive dashboard to provide insights into the attrition (turnover) rates.

<img width="722" alt="image" src="https://github.com/irenhajnal/HR-Analytics/assets/122035130/84362595-27f0-4394-b950-298056445eba">

### Data Source
HR Data: The dataset used for this analysis is the "HR Data.xlsx" file containing detailed information about employees. The dataset has 41 columns and 1,468 rows.

### Tools
- Power BI - Transforming the data in Power Query Editor and Creating Reports

### Data Cleaning and Preparation
In the initiaal data preparation phase, I performed the following tasks:
1. Data loading and inspection
2. Data quality check in Power Query Editor

### Data Visualization
---
#### KPI’s
The dashboard provides insights into key performance indicators (KPIs) related to employees. This enables users to make informed decisions, monitor their progress, and identify trends and opportunities for growth.
  1. Headcount Overview:
      - Overall Employees: all employees including active and incactive headcount
      - Active Employees: total heacount of active employees 
 2. Attrition Overview:
      - Attrition: total headcount of employees which have left the company
      - Attrition Rate: percentage (%) of the employees which have left the company
3. Age Overview
      - Average Age:  average age of active employees
     
#### Charts
  1.	Attrition by Department: A pie chart illustrating the attrition headcount and percentage by department.
  2.	Attrition by Education Field: A bar chart that displays the attrition rates by education field.
  3.	Attrition Rate by Gender for each age groups: The multiple donut charts display how many employees left the company in each of the age groups, the distribution by gender expressed in headcounts and in percentages.
  4.	No of Employees by Age Group: A stacked bar chart that displays the headcount by age group and by gender.
  5.	Job Satisfaction Rating: A matrix chart that presents the distribution of job satisfaction ratings in that particular job. 1 is the lowest(not satisfied at all) rating and 4 the highest (fully satisfied). This is a heat map where lighter shades represent lower count of ratings and darker shades represent higher count of ratings. For example: For Sales Executives the darker colour in column 1 means that with 69 (21%) employees are not satisfied with their job, which is quite high. 
     
### Functions Used ###
- Aggregation functions (DAX language): created New Measures
- Data Tranformation in Power Query Editor (M language): added calculated columns
  
               = Table.AddColumn(#"Changed Type1", "Attrition Count", each if [Attrition] = "Yes" then 1 else 0)
               = Table.AddColumn(#"Changed Type2", "Age Group Sort", each if [CF_age band] = "Under 25" then 1 else if [CF_age band] = "25 - 34" then 2 else if [CF_age band] = "35 - 44" then 3 else if [CF_age band] = "45 - 54" then 4 else 5)
  
### Results and Findings
The analysis results are summarized as follows:
1. The total number of employees is 1,470 out of which 1,233 are active.
2. The attrition rate is 16.12%.
3. The average age of employees is 37 years old.
4. The department with the highest attrition rate is Research and Developement (56.12%) followed by Sales (38.82%).
5. The age group with the highest attrition rate is Under 25 (39.18%) followed by 25-34 (20.22%).
6. The education field with the highest attrition rate is Human Resources (25.93%).
7. Sales Executive has the highest number of employees (326) followed by Research Scientist (292) and Laboratory Technician (259).

### Recomendations
**1. Investigate High Attrition Rates:** The dashboard highlights a concerningly high overall attrition rate (16.12%). According to experts, healthy organizations have an attrition rate of 10% or less. Investigate the reasons behind this, particularly in departments like R&D (56.12%) and Sales (38.82%). Conducting exit interviews or stay interviews with employees who are leaving or considering leaving can shed light on specific factors driving attrition.

**2. Focus on Retention Strategies:** Once the reasons for high attrition are understood, the HR should develop targeted retention strategies. This might involve improving compensation and benefits packages, offering more career development opportunities, or creating a more positive work-life balance for employees.

**3. Address Attrition in Specific Age Groups and Education Fields:**  The data suggests higher attrition rates for employees aged 24 or less (39.18%) and those with a background in Human Resources (25.93%).  Delve deeper to understand why these specific groups are leaving.  Are there growth opportunities lacking for these employees? Are they feeling undervalued?

**4. Analyze Sales Representative Role:**  While not directly related to attrition, the high number of employees in the Sales Executive role (326) compared to others (Research Scientist: 292, Laboratory Technician: 259) is worth exploring.  Are there opportunities to streamline processes or optimize the structure of the sales team?

**5. Improve HR Department Stability:**   The  eye-catching  attrition rate within the Human Resources educational field itself (25.93%) requires immediate attention.  This could be impacting the overall effectiveness of HR initiatives.  Investigate why employees are leaving the department and take steps to improve its stability and morale.


Reference [Youtube](https://www.youtube.com/watch?v=-sOHVl_iCHA&list=PLO9LeSU_vHCWUvkE1FrGeNxSve7YtJrYl)
