# Linear Regression Models, replicating a paper - “Schools Matter: The Positive Relationship Between New York City High Schools’ Student Academic Progress and School Climate”

## Project Overview
The paper I will be attempting to recreate is “Schools Matter: The Positive Relationship Between New York City High Schools’ Student 
Academic Progress and School Climate” by Jonathan Ryan Davisa and Nathan Warner. The authors ran 3 separate linear regression models: 
a first one regressing components of school climate against student school academic progress, the second one regresses student 
background variables against student school academic progress, and the third one combines variables from both models. The reason for 
using different models is to compare the significance of effects from the 2 variable groups and make a judgement on which is more important.

### My approach
The result I will be focusing on is the conclusion that school climate correlates with student academic progress more than student
background factors do. The reason I focus on this conclusion is because it is the main argument throughout the discussion of results
in the paper and is the main contribution being made to the field, as the authors discuss these findings in comparison to other work
suggesting the opposite. To evaluate this finding, I will use cross-validation to compare the 2 main models as well as test whether
this conclusion holds were the data focused on a specific type of school or setting, using always prediction error as the measure for
comparison.

My full analysis is available at this link: https://drive.google.com/file/d/1UTIBuhFtLQCmvOZz4nKSCpCzu9w00_uq/view?usp=sharing
The code is in R and uses the following packages: ggplot2, dplyr, tidyerse and magrittr.

## Data Exploration
The analysis in the paper is based on many variables with the dependent variable being the High School Academic Progress Score
calculated every year by the NYCDOE in the progress report, and the following list of independent variables:

From the NYC School Survey:
- Parent, teacher, and student school climate, the average of each group’s responses to the NYC yearly School Survey.
- Parent, teacher, and student School Survey Responses on Safety and Respect, Engagement, Community, and Academic
Expectations separately.

From NYC Demographics and Accountability Report:
- Percentage of students eligible for free and reduced lunch.
- Total enrolment per school.
- Percentage of English language learners.
- Percentage of special education students.
- Percentage of Black and Hispanic students.
- Percentage of male students.
- Eighth grade Maths ELA score average per school.
- High school level of selectivity.

All this data is reported by the NYCDOE for the 2010-2011 fiscal year, as found in the paper.
Graphs for the most important variables' distributions is on my full analysis document (https://drive.google.com/file/d/1UTIBuhFtLQCmvOZz4nKSCpCzu9w00_uq/view?usp=sharing)

## Data Analysis
I have reproduced all results mentioned in the paper throught the following statistical tools:
- Correlation Matrix of all variables.
- Model 1: Regression of High School Academic Progress against School Climate variables for parents, teachers and students.
- Model 2: Regression of High School Academic Progress against all background variables in addition to 8th grade maths ELA score averages.
- Model 3: Regression of High School Academic Progress against independent variables from both Model 2 and Model 1.
- Model 4: Regression of High School Academic Progress against components of School Climate variables for parents, teachers, and students.

I zone in on models 1 and 2, as the focus of the analysis, and conduct k-fold cross validation to compare them.

![image](https://github.com/user-attachments/assets/d92b1d5e-d1f7-4a87-ba6f-5cb75b189d7e)

I then introduce modification to attempt and reduce prediction error. I segment the data by high school borough, using the Bronx and Manhattan as examples:

![image](https://github.com/user-attachments/assets/54f0c6b6-602b-4c0b-a485-e21ec470f947)

![image](https://github.com/user-attachments/assets/b5057fd2-53dd-42e5-b5ff-b284df784dbc)

I also introduce interactions to model 2 and compare it once again to model 1.

![image](https://github.com/user-attachments/assets/88e67293-ad94-4a62-ac46-89e1b94318ca)

## Conclusion
Despite changes in the data set and in the model itself, the conclusion that perceptions of school climate are better predictors of school academic progress from the paper holds each time. 
If I were to re-attempt bettering these models once again, I would look to ideally use disaggregated data, meaning per student not at the school level only, or use a larger dataset, meaning beyond NYC.


