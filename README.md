# School District Analysis

## Project Overview
#### A local city school district is looking to analyze standardized math and reading test scores of all the high schools in the district. Additionally, the data from the students and schools was refactored to show various aspects of the schools within the school district and how well the students in the schools are performing respectively. Average tests scores, the percentage of students passing the tests, the spending per student, and the type of school were all evaluated to better assist the school district in better understanding the areas for growth. After discovering academic dishonesty amongst the 9th grade math scores at Thomas High School, the data was re-calculated to exclude the fraudulent scores. 

## Resources Utilized
##### Data Source: schools_complete.csv
##### Software: Python 3.7.6; Anaconda 4.10.3

## Results
#### 
*	As indicated in the images below, the Average Math Score decreased from 79.0 to 78.9, the % Passing Math decreased from 75.0% to 74.8%, and the % Overall Passing decreased from 65.2% to 64.9%

***Original District Summary***
![Original District Summary](https://user-images.githubusercontent.com/99554642/159127538-34675448-18cc-4f50-ab4e-e164dfac3b9d.png)

***Updated District Summary***
![Updated District Summary](https://user-images.githubusercontent.com/99554642/159127541-f62d9c67-3250-4c29-a092-bcef6bf550aa.png)


*	By replacing the values for percentage passing with the data from only 10-12th graders, the school summary for Thomas High School indicated an increase in % Passing Math, % Passing Reading, and % Overall Passing as indicated in the following images.

***Original School Summary***
![Original School Summary](https://user-images.githubusercontent.com/99554642/159127545-b5f11ee2-5938-4bb3-a862-222cbce68a48.png)

***Updated School Summary***
![Updated School Summary](https://user-images.githubusercontent.com/99554642/159127548-4a041abb-61a7-4558-b9de-79ca666487cd.png)

*	Replacing the values mentioned above allowed Thomas High School to be ranked second overall in the district for % Overall Passing.
*	Additionally, replacing the scores for the 9th graders at Thomas High school had the following effects:
    * Scores by school spending from $585-629 and $630-644 showed an increase in % Passing Math, % Passing Reading, and % Overall Passing.
    * No effects were observed in the scores by school size as all values remained the same.
    * Similarly, no effects were observed in the scores by school type.
    * No effects were noted outside of the math and reading score values for 9th graders at Thomas High School; those values were both replaced by NaN as intended by the following code:
```
student_data_df.loc[((student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th")),"math_score"] = np.nan
```

## Summary
Replacing the values for the ninth graders from Thomas High School with Nan have several implications for the rest of the school district data. The first major change was observed in the district summary, which was calculated after replacing the ninth grade scores, but before replacing the percentage metrics with the data from the 10th-12th graders. At that point, the district summary indicated an overall decrease in Average Math Score, % Passing Math, and % Overall Passing. After replacing the scores with the scores from 10-12th graders, an increase was observed in the % Passing Math, % Passing Reading, and % Overall Passing for Thomas High School, which then had a ripple effect. The scores by school spending increased in the range from $585-644 increased in Average Math Score, Average Reading Score, and subsequently the percentage of passing math, reading, and overall passing scores. Ultimately, by replacing the values, Thomas rose to be ranked second in the school district for percent of students overall passing their math and reading standardized tests.
