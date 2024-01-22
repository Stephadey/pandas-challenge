#  Module 4 Challenge

In this assignment, you’ll create and manipulate Pandas DataFrames to analyse school and standardised test data.

### Background

You are the new Chief Data Scientist for your local government area. In this capacity, you'll be helping the school board and mayor make strategic decisions regarding future school budgets and priorities.

As a first task, you've been asked to analyse the area-wide standardised test results. You'll be given access to every student's maths and reading scores, as well as various information on the schools they attend. Your task is to aggregate the data to showcase obvious trends in school performance.

### Instructions

Using Pandas and Jupyter Notebook, create a report that includes the following data. Your report must include a written description of at least two observable trends based on the data.

**Hint:**  Check out the sample solution called  `PyCitySchools_starter.ipynb`located in the .zip file to review the desired format for this assignment.

#### Local Government Area (LGA) Summary

Perform the necessary calculations and then create a high-level snapshot of the local government area's key metrics in a DataFrame.

Include the following:

-   Total number of unique schools
    
-   Total students
    
-   Total budget
    
-   Average maths score
    
-   Average reading score
    
-   % passing maths (the percentage of students who passed maths)
    
-   % passing reading (the percentage of students who passed reading)
    
-   % overall passing (the percentage of students who passed maths AND reading)
    

**Note:**  A passing grade is 50 or higher.

#### School Summary

Perform the necessary calculations and then create a DataFrame that summarises key metrics about each school.

Include the following:

-   School name
    
-   School type
    
-   Total students
    
-   Total school budget
    
-   Per student budget
    
-   Average maths score
    
-   Average reading score
    
-   % passing maths (the percentage of students who passed maths)
    
-   % passing reading (the percentage of students who passed reading)
    
-   % overall passing (the percentage of students who passed maths AND reading)
    

#### Highest-Performing Schools (by % Overall Passing)

Sort the schools by  `% Overall Passing`  in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".

#### Lowest-Performing Schools (by % Overall Passing)

Sort the schools by  `% Overall Passing`  in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

#### Maths Scores by Year

Perform the necessary calculations to create a DataFrame that lists the average maths score for students of each year level (9, 10, 11, 12) at each school.

#### Reading Scores by Year

Create a DataFrame that lists the average reading score for students of each year level (9, 10, 11, 12) at each school.

#### Scores by School Spending

Create a table that breaks down school performance based on average spending ranges (per student).

Use the code provided below to create four bins with reasonable cutoff values to group school spending.

```python
spending_bins = [0, 585, 630, 645, 680]
labels = ["<$585", "$585-630", "$630-645", "$645-680"]

```

Use  `pd.cut`  to categorise spending based on the bins.

Use the following code to then calculate mean scores per spending range.

```python
spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

```

Use the scores above to create a DataFrame called  `spending_summary`.

Include the following metrics in the table:

-   Average maths score
    
-   Average reading score
    
-   % passing maths (the percentage of students who passed maths)
    
-   % passing reading (the percentage of students who passed reading)
    
-   % overall passing (the percentage of students who passed maths AND reading)
    

#### Scores by School Size

Use the following code to bin the  `per_school_summary`.

```python
size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

```

Use  `pd.cut`  on the "Total Students" column of the  `per_school_summary`DataFrame.

Create a DataFrame called  `size_summary`  that breaks down school performance based on school size (small, medium, or large).

#### Scores by School Type

Use the  `per_school_summary`  DataFrame from the previous step to create a new DataFrame called  `type_summary`.

This new DataFrame should show school performance based on the "School Type".

## **Summary of Analysis**

Based on the comprehensive analysis conducted on the provided school and student data, several key insights and trends have emerged regarding the performance and characteristics of schools within the local government area. The analysis covered various aspects, including overall district summaries, school-wise performance, and the impact of factors like school size, type, and budget on student outcomes.

1.  **Local Government Area (LGA) Summary**:

-   This provided a high-level overview of the district, including total schools, students, budget, and average scores. The data revealed the overall performance of the district in terms of maths and reading proficiencies.

3.  **School Summary**:

-   Each school was individually analysed for metrics such as type, number of students, budgets, average scores, and passing percentages. This detailed analysis offered insights into the performance of each school within the district.

5.  **Performance by School Size, Type, and Budget**:

-   Schools were categorised based on their size, type (Government or Independent), and spending per student. These categorisations allowed for comparisons to understand how these factors correlate with student achievement.

7.  **Maths and Reading Scores by Year**:

-   The analysis of average scores by year level across schools provided an understanding of academic performance consistency and variation over different year levels.

**Conclusions and Comparisons**

1.  **Impact of School Size on Performance**:

-   One notable trend was the relationship between school size and student performance. Smaller schools (with fewer than 1000 students) tended to have higher overall passing rates compared to larger schools. The analysis showed that smaller schools had an average overall passing rate of approximately 79%, which was higher than the approximately 70% observed in large schools (2000-5000 students). This suggests that the more personalised attention possible in smaller school settings might positively influence student outcomes.

2.  **Influence of School Type on Academic Outcomes**:

-   Another significant observation was the difference in performance between Government and Independent schools. Independent schools generally showed higher average scores and passing percentages in both maths and reading compared to Government schools. The data revealed that Independent schools had an average overall passing rate of around 77%, compared to approximately 71% for Government schools. This indicates that Independent schools might be better equipped in terms of resources or methodologies, leading to improved academic performance.

**Additional Insights from the Analysis**

-   **LGA Summary**: The district's average maths score was around 70.34%, and the average reading score was approximately 69.98%, indicating a moderately high level of proficiency across the schools.
-   **School Summary**: The performance of schools varied, with some schools showing exceptional results, like Griffin High School with an overall passing rate of about 81.34%, while others like Ford High School had lower rates at around 67.47%.
-   **Performance by Budget**: Interestingly, schools with lower spending per student (e.g., <$585) had comparable or better performance metrics than schools with higher spending ranges, challenging the assumption that higher spending directly correlates with better academic outcomes.
-   **Year-wise Performance Trends**: The analysis of maths and reading scores by year level suggested that there was not a significant fluctuation in scores from year 9 to year 12, indicating a consistency in academic performance across different year levels in schools.
##
### References

Data generated by  [Mockaroo, LLC](https://mockaroo.com/), (2022). Realistic Data Generator. Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
