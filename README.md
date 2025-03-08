# Exploring Data Analysis of factors that contribute to student nath scores
## Project Overview:

![image](https://github.com/user-attachments/assets/80803e3a-3609-48d0-bbeb-29ee38492ce6)






U.S. students' math scores fall behind when compared to those of many other developed countries. This is evident by the 2022 Programme for International Student Assessment results. The U.S. ranked 18th in math amoung the participating countries. U.S. students averaged a score of 489.3 which was below the average score of 494 and significantly behind the top scores of 559.7.

These scores showed a drop of 13 points compared to the results from 2018. 

**What factors contribute to student math performances?**

The goal of this project is to analyze data from a dataset of 1,000 students and gain insight on factors that contribute to performances in math.

Identifying factors that contribute to math performances will help inform schools and policy makers:

### Use Cases

Insights gained from this project can help schools identify controlable factors that improve student math performance.


## Data
Dataset can be downloaded from Kaggle: [Student Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)

## Exploratory Data Analysis:

### Do students from lower socio-economic status (free/reduced) score lower on math assessments?

64% of students in the data set are on standard lunch and 35.5% are on free/reduced lunch. This indicates that the dataset in imbalanced. To determine if socio-economic status is a factor I will perform a t-test to determine if there is a difference in average scores between these groups and if that difference is statistically significant. 

[Boxplot of Lunch status and math scores] 

![image](https://github.com/user-attachments/assets/a6ab2e67-8bad-4911-8a43-2cab8f63d8fe)


### Hypothesis testing:
Null Hypothesis: The observed difference in math scores between standard and free/reduced lunch is due to chance.

Alternative Hypothesis: the observed difference in math scores between standard and free/reduced lunch is not due to chance.

### T-test:

(<img width="829" alt="image" src="https://github.com/user-attachments/assets/f71b691b-a372-431d-a7ba-2f85b5da1d03" />
)

### Conclustion on EDA for socio-economic status and maths scores:
A t-statistic score of +/- 2 signifies that there is not significant difference between the means of both groups. The t-statistic of our groups is +11. This signifies that there is a very large difference between the math scores of standard and free/reduced lunch.

The p-value is far below 5% and is 00000000000000000000000000554% which is very close to zero.

The p-value tells us that there is an extremely small probability that this observed difference happened by random chance.

I must reject the null hypothesis: The difference in math scores between standard and free/reduced is due to chance.

### Possible Confounding Variables:
The difference may not be due just to socio-economic status but other confounding factors such as (race/ethnicity, gender, parental level of education lunch test preparation course)

I must explore these variables further to gain deeper understanding of factors that contribute to math scores.

### EDA Gender and Math Scores:
![Gender Historgram Visualization] (<img width="889" alt="image" src="https://github.com/user-attachments/assets/3bfbcccb-1218-4706-a0b8-8a192d342c3c" />
)

### Gender Boxplot

![image](https://github.com/user-attachments/assets/e9405cbe-8d2b-46ff-b101-8d6ff102e807)


### Hypothesis Testing: Gender

Null Hypothesis: The observed difference in math scores between males and females is due to chance.

Alternative Hypothesis: The observed difference in math scores between males and females is not due to chance.

### Conclusion on Gender:
A t-statistic score of +/- 2 signifies that there is not significant difference between the means of both groups. The t-statistic of our groups is -5.3. This signifies that there is a difference between the math scores of males and females in this dataset.

The p-value is far below 5% and is 0.000000084% which is very close to zero.

The p-value tells us that there is an extremely small probability that this difference happened by random chance.

I must reject the null hypothesis: The difference in math scores between males and females is due to chance.

### EDA on Race/Ethnicity: Is there a correlation between race/ethincity and math scores?
Race/Ethnicity Distribution in the dataset



<img width="617" alt="image" src="https://github.com/user-attachments/assets/0efb2b34-fe57-4b1f-8bcb-33efdaefae9a" />



### Boxplot of Math score by Race/Ethnicity:

![image](https://github.com/user-attachments/assets/c1645f32-580b-4da4-9595-ec602af0a09d)

### Observations: Group E and D have the highest average scores at 73 for group E and 67 for group E.

Group A has the lowest average score at 61 and group B has an average score of 63. Race/Ethnicity does seem to be a factor but are these results due to chance?

### Welch's ANOVA test: A simple T-test would not work here since there are several race/ethnicity groups. Therefore Welch's ANOVA test would be the most appropriate.

![image](https://github.com/user-attachments/assets/650e1829-2f20-4fd3-b11e-460b8942a97a)

### Conclusiong based on Welch's ANOVA: After performing a Welch's ANOVA test I must conclude that there is not sufficient evidence to determine that the differences observed in math score are due to race/ethnicity. The p-value was.19 which is greater than the standard of .05.


### EDA: Parental level of eduation and math scores.

![image](https://github.com/user-attachments/assets/feaeca24-93d7-46f9-ab51-cb2921323eac)

### Observations: There seems to be a correlation between parental level of education and average math score. Students who's parents only completed high school averaged the lowest score with a 62 on their math score while students who's parents earned a masters degree earned the highest average score at 69.74.


### ANOVA Test on parental level of education and math scores.

![image](https://github.com/user-attachments/assets/d6a7cdd6-c65f-466f-bafd-42ec7af1f3e9)

### ANOVA Results: Based on these results I can conclude that there is a statistically significance between math scores and different levels of parent education. 

### Conclusion based on Parental level of Education and Math Scores:

Higher parental education is associated with higher math scores. The biggest difference in math scores is between students whose parents have a master's degree vs. high school diploma, with an average difference of 7 points. There also seems to be no significant difference between master's and bachelor's which could be interpreted as diminishing returns.



### EDA on test preperation courses and math scores

![image](https://github.com/user-attachments/assets/4d4c592d-c11c-48e0-93f3-c81223f804af)

### Observation: 642 students did not take test preperatio courses and 358 did. The average score of those who took test preperation courses was 69 and the average of those who did not was 64.

### Hypothesis testing on test preperation courses completed. 

### Hypothesis: The difference in test scores between students who took test preperation courses and those who did not is due to chance.

![image](https://github.com/user-attachments/assets/643b620c-9c54-4da8-8837-5bdb180424fc)

### EDA test prep conclusion:

### Given that the average test scores of students who did not prepare for the test is 64 vs those who did is 69. This difference is statistically significant at a p-value fare below 5%, however I can not conlcude that this difference is average score is due only to test preperation variable as there could be confounding variables unaccounted for. For example a student might not have done test prep because they could be from lower socio-economic status and such prep would require payment or transportation ect. The only thing that can be concluded from this is that there is a difference in average math score between those who did test preperation and those who did not.


### Correleation Matrix:

![image](https://github.com/user-attachments/assets/74c492cb-ed39-4c63-a2d8-d7c1b3ef54ec)


### Observations based on correlation matrix:

The top three positive correlatated features for math scores are lunch standard with a correlation score of .35, this indicates that students from higher income familes tend to perform better in math. Next highest correlated feature with math score is race/ethnicity E. This indicates that students in this race/ethincity group earned higher math scores. Test preperation course completed also had a positive correlation of .18 and male students had a positive correlation with higher math score at .17.







