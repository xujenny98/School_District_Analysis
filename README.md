# School_District_Analysis

# Background
<br/>The grades of the ninth graders at Thomas High School have been changed. While administrators do not know the full extent of this academic dishonesty, they want to uphold the standards of state testing and have turned to you for help.

After assessing the situation with the school superintendent and Maria, you decide the best approach is to:
<br/>-Replace the ninth-grade math and reading scores from Thomas High School.
<br/>-Keep all other data associated with the ninth-grade students and Thomas High School intact.

# Objectives
**The goals of this challenge are for you to:**
<br/>-Filter DataFrames using logical operators.
<br/>-Replace the incorrect values with NaN.
<br/>-Explain how your PyCitySchools analysis changes after you handle the incorrect data.

# Results
<br/>**How is the district summary affected?**
    <br/> *BEFORE DATA CLEANUP
    <br/> *Average Math Score, Average Reading Score, % Passing Math, % Passing Reading, % Overall Passing
    <br/> *79.0, 81.9, 75, 86, 65
    <br/> *AFTER DATA CLEANUP
    <br/> *Average Math Score, Average Reading Score, % Passing Math, % Passing Reading, % Overall Passing
    <br/> *78.9, 81.9, 74, 85, 64
    <br/> *OBSERVATION: Slight downward change in district averages
    ![Districtsummary](https://user-images.githubusercontent.com/77771292/111103781-967d2480-8525-11eb-88f6-5c906ded943a.png)
<br/>**How is the school summary affected?**
    <br/> *BEFORE CLEANUP: Thomas High School's % Overall Passing = 91, placing second
    <br/> *AFTER CLEANUP: % Overall Passing = 65, placing eighth!
    <br/> *OBSERVATION: Overall ranking order change due to THOMAS HS, which slipped from 2ND to 13TH position, with the other intervening schools moving up.
    <br/> *Recalculate the high- and low-performing schools.
![Screen Shot 2021-03-15 at 12 31 58 AM](https://user-images.githubusercontent.com/77771292/111103923-e1973780-8525-11eb-90bf-b92fdc1d93e7.png)
<br/>**How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance, relative to the other schools?**
    <br/> *OBSERVATION: Relative ranking for THOMAS HS changed from 2ND to 8TH, as it's % OVERALL PASSING number decreased from 91% to 65%.
    <br/> *Recalculate the scores by grade, scores by school spending, scores by school size, and scores by school type.
<br/>**How does replacing the ninth-grade scores affect the following?**
<br/>**Math and Reading Scores by Grade**
    <br/> *Thomas HS 9th grade math & reading scores set to "nan" and equivalent to 0
    <br/> *Totals for passing math & reading across grades are reduced as all of 9th grade scores are equivalent to failing
    <br/> *Average scores calculation not significantly affected by removal of 9th grade scores, seems due to count() function NOT including 9th grade scores = nan
    <br/> *Cacluate number of students with a math grade - use "student_school_math.groupby(["school_name"]).count()""
    <br/> *BEFORE cleanup: Thomas High School       1635
    <br/> *AFTER cleanup: Thomas High School       1174
    <br/> *"%age passing" score is reduced as Total number of students (denominator) remains unchanged, but total passing value (numerator) is reduced by the number of removed 9th grade scores.
![Screen Shot 2021-03-15 at 12 40 53 AM](https://user-images.githubusercontent.com/77771292/111104443-1bb50900-8527-11eb-8eaf-909fd9db5e30.png)
<br/>**Scores by School Spending**
    <br/> *Thomas HS is in the spending bucket "$630-644"
    <br/> *Removing 9th grade scores reduces the "% Passing Math", "% Passing Reading" and "% Overall Passing" scores for spending bucket "$630-644" as follows
    <br/> *BEFORE: 73, 84, 63
    <br/> *AFTER: 67, 77, 56
![Screen Shot 2021-03-15 at 12 42 10 AM](https://user-images.githubusercontent.com/77771292/111104518-4901b700-8527-11eb-882d-6ed667f50787.png)
<br/>**scores by School Size**
    <br/> *Thomas HS is in the "Medium (1000-2000)" size bucket
    <br/> *Removing 9th grade scores reduces the "% Passing Math", "% Passing Reading" and "% Overall Passing" scores for size
    <br/> *bucket "Medium (1000-2000)" as follows
    <br/> *BEFORE:94, 97, 91
    <br/> *AFTER: 88, 91, 85
<br/>**Scores by School Type**
    <br/> *Thomas HS is in the "CHARTER" type bucket
    <br/> *Removing 9th grade scores reduces the "% Passing Math", "% Passing Reading" and "% Overall Passing" scores for type bucket 
    <br/> *"CHARTER" as follows
    <br/> *BEFORE:94, 97, 90
    <br/> *AFTER: 90	93	87
![Screen Shot 2021-03-15 at 12 43 36 AM](https://user-images.githubusercontent.com/77771292/111104629-7d757300-8527-11eb-8685-5825c9423083.png)

