# SOA-Student-Success
SOA Predictive Analytics sample project called Student Success

Problem:
We have just been presented a unique opportunity to work with School Wiz, a group dedicated to providing remedial education to troubled students. School Wiz has heard about our work and wants to explore using our services to advance their business goals. If we secure their business, we will be working with them for the next several months on data collection and analysis. However, they are not yet convinced that predictive analytics can help them. 
To earn their business, we need to demonstrate how we can use our tools to answer their major questions, which are:
  1. How accurately can we predict which students will pass based on a variety of factors; and
  2. Which factors are most important for predicting pass rates?

Executive Summary:

School Wiz is a group dedicated to providing remedial education to troubled students. The organization has been trying to better understand their students through data collection, analysis and advanced predictive analytics. As leaders of the industry, Sharpened Consulting has been tasked with using advanced analytical tools to better understand the factors affected remedial education of troubled students. For the purpose of this analysis, we will focus on two major aspects: the factors that are most important for predicting pass rates and how accurately can we predict which students will pass based on specific factors.
The preliminary dataset provided by School Wiz contains 29 predictor variables that were collected prior to students entering the formal school year. As the grades for each trimester are heavily correlated, we opted to focus on the grade for the final trimester. The data collected includes personal information of the students and their parents. It is important to ensure that the collection and use of data complies with ASOP 23 and other local regulations that may apply.

For the purposes of our analysis, we manipulated the dataset to better represent the success rate of students. We removed any missing values and only looked at G3 values between 0 and 20 due to the grading scale. Both, the mother’s and father’s education is assesses on a scale from 0 to 5. As a value of 0 was unclear we removed any students whose parents had an education level of 0. After assessing the correlation of variables, we created three new features. The first feature combined the total education levels of the mother and father to calculate whether both parents went to college. The second feature calculated the total alcohol consumption level. The third feature showed whether the student had failed any prior classes. 

We used a generalized linear model (GLM) using a binomial function to predict whether a student would pass. For easier interpretability, we decided to use the logit link function. The model would calculate the log odds of a student passing based on the predictor variables. The GLM model is flexible and easily interpretable. The nature of the model allows us to remove variables and understand how that affects the fit of the model, measured through AIC. The model also handles categorical variables very well. However, as this is a parametric model, the model will be unable to find non-linear relationships that may positively contribute to the predictive power of the model.

After developing various models, we concluded that the following GLM model exhibits the greatest predictive power using stratified sampling in a validation-set approach with train-test datasets:

  •	Sex - student's sex (binary: female or male)
  
  •	Medu – mother’s education (numeric: from 0 to 4 a)
  
  •	Fedu - father's education (numeric: from 0 to 4 a)
  
  •	Mjob - mother's job (nominal b)
  
  •	Traveltime - Home to school travel time (1 - <15 minutes, 2 - 15 to 30 minutes, 2 - 30 minutes to 1 hour or 4 - > 1-4 hours)                
                 
  •	Failures - number of past class failures (numeric: n if 0 n < 3, else 3)
  
  •	Famsup - extra family supplement (binary: yes or no)
  
  •	Nursery - attended nursery school (binary: yes or no)
  
  •	Higher - wants to take higher education (binary: yes or no)
  
  •	Internet - internet access at home (binary: yes or no)
  
  •	Gout - going out with friends (numeric: 1 - very low to 5 - very high)
  
  •	Health - current health status (numeric: from 1 - very bad to 5 - very good)
  
  •	Comb.edu – the combined education score for both mother and father (out of 16)
  
  •	Both.coll – did both parents attend college (Binary: 1 = Yes, 0 = No)

The final model displayed an accuracy of 77.09%. This means that the model will predict with 77% accuracy if a student is likely to pass the class in the third trimester. We observed that goout was an excellent predictor and an increase in the student going out would decrease the chances of the student passing. Another important variable was the failures variable. If a student had failed prior classes, the student was much more likely to fail the trimester. 

We believe that the initial model developed to predict student success provides sufficient predictive power based on the variables assessed. We believe that, give more time, we can develop a better model, with additional variables, that will be abe to better predict student success in a class.
