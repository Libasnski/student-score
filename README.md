# Student-Score Analysis

### Project Overview
My project aims to analyze a dataset containing information about the performance of senior students at a fictional high school during their final semester. The dataset includes various attributes such as academic scores in different subjects, participation in extracurricular activities, part-time job status, absence days, self-study hours, and career aspirations.

### Objective:
The primary objective of the project is to gain insights into factors influencing student performance and behavior. By analyzing the dataset, the project seeks to answer questions related to academic achievement, extracurricular involvement, part-time job impact, attendance patterns, self-study habits, and career aspirations among students.

### Data source

student score:The primary dataset used for this analysis is "student_score.csv" file containing detailed information about students performance on various subjects.

### Tools

- Excel -Data cleaning.[download here](https://microsoft.com)
- SQL server -i used all my analysis on sql to manipulate and analyse data
- Tableau - i used  Tableau for data visualization.

### Data Cleaning/Peparation

  In the initial data preparation phase,i performed the following tasks:
  
 1. Data loading and inspection,
  
 2. Looking for duplicates,
  
3.  Handling missing values,
  
 4. Data cleaning and formatting

### Exploratory Data Analysis

EDA involves exploring student score data to answer key questions such as:

- Is there a correlation between students' participation in extracurricular activities and their academic performance across different subjects?
- Do students who work part-time have lower or higher academic scores compared to those who don't work? Is there a difference in performance based on gender?
- What is the distribution of career aspirations among students, and does it vary based on gender? Are there any trends or patterns in career choices?
- How does the number of absence days correlate with students' academic performance? Are students with higher absence rates more likely to have lower scores?


### Data Analysis
Here is my data analysis codes to answer questions:
```sql
select 
  extracurricular_activities,
  avg(math_score) AS avg_math_score,
  avg(biology_score) AS avg_biology_score,
  avg(physics_score) AS avg_physics_score,
  avg(chemistry_score) AS avg_chemistry_score,
  avg(geography_score) AS avg_geography_score,
  avg(history_score) AS avg_history_score,
  avg(english_score) AS avg_english_score

from `liban-414707.student_score.students`

group by 
    extracurricular_activities

```
```sql
  select 
  part_time_job,
  gender,
  avg(math_score) AS avg_math_score,
  avg(biology_score) AS avg_biology_score,
  avg(physics_score) AS avg_physics_score,
  avg(chemistry_score) AS avg_chemistry_score,
  avg(geography_score) AS avg_geography_score,
  avg(history_score) AS avg_history_score,
  avg(english_score) AS avg_english_score

from `liban-414707.student_score.students`

group by 
    part_time_job,
    gender
```

```sql
select
  career_aspiration,
  gender,
  count(career_aspiration) AS total_career_num

from
  `liban-414707.student_score.students`

group by
   career_aspiration,
   gender

order by
   total_career_num desc,
   gender,
   career_aspiration
```
### Results/Findings

1.extracurricular activities does not relate to student academic performance.When you campare the performance on subjects students who involved and those who didn’t participate almost scored the same score.

2.students who work part time have lower academic performance compared to those who don’t work.The average score tends to be higher on those students who don’t work.There is no much difference on in performance on genders there is slight difference on the score between females and males who work just the average point of 1.

3.There are notable differences in the number of males and females aspiring to become bankers. Females have a higher count (103) compared to males (66). This could indicate a trend where more females aspire to pursue careers in banking.
Conversely, in the field of software engineering, there's a higher count of males (174) compared to females (141), suggesting a trend where more males are interested in software engineering careers.
In professions like accountant, artist, and doctor, the counts are relatively close between genders. For example, the count for accountants is 64 for females and 62 for males, indicating a relatively balanced interest in this field among both genders.
Some professions, like construction engineer and stock investor, have a notable gender disparity. For instance, there are 68 males aspiring to become construction engineers compared to no females, indicating a potential underrepresentation of females in this field.

4.The higher the number of days absent the lower the performance.There strong correlation between absenteeism and performance

## Recommendations

- Flexible Schedules: Encourage part-time employers to offer flexible schedules that accommodate students' academic responsibilities, reducing the need for excessive absenteeism.
- Time Management Skills: Implement workshops or seminars to help students develop effective time management skills, enabling them to balance work and study commitments more effectively.
- Remote Work Opportunities: Explore remote work options for part-time jobs, allowing students to work from home and potentially reducing commuting time and schedule conflicts.
- Prioritization: Encourage students to prioritize their academic commitments over part-time work when necessary, emphasizing the importance of maintaining a balance between work and study.

















  
