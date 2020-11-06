# SOA Mine Safety Ratings
Problem:

The union would like to give functioning mines in the United States a simple five-star safety rating to help their members when choosing where to work and negotiating hazard pay. They think they have a good understanding of what factors drive mine safety, but they want us to offer an independent, data-driven analysis so that they can validate and refine their opinions. They pointed us to national mine data in the attached csv file. They asked our analytics firm for the following:
  1. Two models, using different approaches, that will predict the rate of injuries per 2000 employee hours for a given mine
  2. A report that identifies the key factors resulting in higher or lower injury rates.


Executive Summary:

The union would like to give functioning mines in the United States a simple five-star safety rating to help their members when choosing where to work and negotiating hazard pay. Actuarial consultants have been tasked to develop an independent, data-driven analysis to validate the union’s understanding of the important factors affecting mine safety. The union has asked the firm to focus on two major aspects: a model that will predict the rate of injuries per 2000 employee hours for a given mine and the key factors resulting in higher or lower injury rates.

The data provided by the union is from the U.S. Mine Safety and Health Administration (MSHA) from 2013 to 2016. Each row represents the safety experience of one mine for one year. The dataset has 20 variables. As the data collects sensitive information about mines, it is important to ensure that the union complies with ASOP 23 and other local legal regulations when using the analysis in developing a five-star safety rating system.

We manipulated the dataset to better assess the various variables affecting injury rates of miners. We removed any missing values and calculated the dependent variable by dividing the number of injuries by the offset, total employee hours divided by 2000 hours. Our preliminary analysis showed that the injury rate per 2000 employee hours was too high due to observations with low total employee hours and closed (or like closed) mines. We removed observations with total employee hours lower than 2000 hours and closed (or like closed) mines. We also created a new variable (MINE_CHAR) that combined Type of mine and commodity. 
This variable was then releveled to make the “Sand & gravel Sand & gravel” the base level. 

We have concluded that the Generalized Linear Model (GLM) with a Poisson distribution to model the rate of injury. We predict the variable exposure we used the total employee hour divided by 2000 as an offset for the number of injuries as the Poisson distribution can only model the count of the dependent variable. The GLM is a flexible model that can be easily implemented and interpreted. We can easily understand how each predictor variable affects the dependent variable and remove any variables that do not have high predictive power. However, the GLM is not good at identifying and modeling non-linear relationships like other non-parametric methods such as Random Forests.

After conducting our analysis on several models, we have concluded that the GLM model with the best predictive accuracy has the following variables using stratified sampling with a validation set (test/train dataset) approach:

•	SEAM_HEIGHT - Coal seam height in inches (coal mines only)

•	PCT_HRS_UNDERGROUND - Proportion of employee hours in underground operations

•	PCT_HRS_MILL_PREP - Proportion of employee hours in mills or prep plants

•	PCT_HRS_OFFICE - Proportion of employee hours in offices

•	MINE_CHAR – Combines the commodity mined and the type of mine

•	LOG_AVG_EMP_TOTAL: PCT_HRS_UNDERGROUND - 

•	LOG_AVG_EMP_TOTAL: PCT_HRS_STRIP

Loosely a Poisson distribution can be interpreted as: a one-unit change in the predictor variable, the difference in the log of the expected counts is expected to change by the regression coefficient of the stated predictor variable. The analysis of the model reveals that MINE_CHAR has a significant impact on the injury rate. Underground mines are more likely to lead to a higher rate of injury as compared to other mines.

