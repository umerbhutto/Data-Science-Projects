# SOA-Hospital-Readmissions
SOA Predictive Analytics sample project called Hospital Readmissions

Problem:
Predictive Modles for hospital readmissions are in high demand due to the US Centers for Medicare and Medicaid Services (CMS) Hospital Readmission Reduction Program. CMS introduced a penalty for excess readmissions which has lead hospitals to look towards predictive analytics to identify patients who are most likely to be readmitted. Hospitals have hired Consultants Inc. to develop a model that can outperform the LACE index, the industry standard when hospital readmission rates. The hospital has tasked us with developing a model that has an AUC value of greater than 0.70. 


Executive Summary:

Predictive models for hospital readmission rates are in high demand due to penalties for excess readmissions under the US Center for Medicare and Medicaid Services (CMS) Hospital Reduction Program. Hospitals currently use the industry’s standard model called the LACE index to predict which patients are at risk of readmission. To better predict the risk of readmission and improve the hospital’s profitability, a group of hospitals has hired Actuarial Consultants Inc. to develop a generalized linear model (GLM) that is superior to the industry’s LACE Index using AUC as the goodness-of-fit indicator. 

The dataset supplied by the hospitals includes 9 variables. Each observation shows the characteristics of the patient. For the purposes of this study and the sensitivity of the data, we need to ensure that the model and any modeling techniques comply with ASOP 23 and other local regulations that may apply.

For our analysis, we changed certain aspects of the dataset. Any missing values were removed. As LOS and HCC.Riskscore were both skewed, we transformed the two variables using the log function. This allowed us to better understand the data. We also created a new variable called Under_65 to determine if a patient was below 65 or not to better evaluate whether a patient was the recipient of Medicare. We also combined DRG.Complication and DRG.Class into one variable called DRG. In order to create a better model, we binarized three variables: Gender, Race and DRG. This allowed us to better evaluate if a level of the mentioned variables was significant when predicting the readmission of a patient.

We used a Generalized Linear Model (GLM) to predict the chances of readmission of a patient. Due to the binary nature of the variable, we used a binomial distribution with a logit link function. The GLM is a flexible model that can be easily interpreted and is excellent in dealing with classification problems. The model allows us to better understand the predictive power and direction of each variable to better evaluate the affect of each variable on the readmission rate of patients. We can also easily remove variables with low predictive power and decrease the complexity of the model. However the model is sensitive to outliers and is unable to handle non-linear relationships well unlike Random Forests. 

After various models, we have concluded that the model with the following variables provides the best predictive accuracy using a validation-set approach (training / testing set with stratified sampling):
  •	Age – the patient’s age in years, an integer
  
  •	Log_LOS – the logarithmic of the length of hospital stay in days, an integer
  
  •	Log_HCC.Riskscore – the logarithmic of the Hierarchical Condition Category risk score.
  
  •	DRGMED…Other – Patients in MED diagnostic related group classification and have other complications
  
  •	DRGSURG…Other – Patients in the SURG diagnostic related group classification and have other complications

The LACE index has a AUC value of 0.70. The GLM model specified above has an AUC value of 0.73 which is far better than the LACE Index.

We were asked to investigate a cost/benefit approach to adopting this predictive model. For the 66,776 patients in our sample, without using the predictive model, 8,409 would be readmitted at a cost of Exam 210,225. Using our predictive model, 39,301 will be predicted to be readmitted and receive an intervention, preventing readmission of 7,313 of the 8,409. The total cost of using the model and selective intervention is 106,002, for a saving of 104,223. We are not able to determine the savings that would have been produced using the LACE index.

Given that the proposed model uses relatively fewer variables, thus decreasing the complexity of the model, and outperforms the LACE index, we recommend additional discussion and testing of the model to further validate its potential use. 
