# Depression Among Students in India - Logistic Regression Analysis

This is an exploratory analysis aimed at identifying the best model to explain depression in students aged 18–34 from Indian cities.  
The analysis does not focus on finding the best predictive model but rather on understanding the data to serve as a foundation for developing a potential causal model. 

The dataset used is open-access data from Kaggle. You can find an overview at [this link](https://www.kaggle.com/datasets/hopesb/student-depression-dataset).  
To see the analysis online go to: http://rpubs.com/MariaRed/1262329. 

Importantly, in this study, depression is a binary variable. Since depression is rarely a categorical condition, it would be better represented on a continuous scale. Therefore, it should be noted that the dataset is based on a rough simplification. Additionally, the results should not be generalized to the entire population but rather only to Indian students aged 18–34. 

**Before running the code**: The original analysis was conducted on an exploratory sample size equal to 5000. However, since it takes a long time to compute, you can change the sample size by changing the value of "exploratory_sample_size". 

The analysis consists of the following steps:

### **1. Exploratory Data Analysis (EDA) Using Random Forests**
I explore the data using the Random Forests method. Random Forests is a non-parametric approach that inherently detects interactions and non-linear relationships while avoiding overfitting. Although considered "black-box" algorithms, Random Forests provide valuable insights for creating an informed parametric model. By identifying the most relevant predictors, they help avoid violating assumptions caused by missing interactions or non-linear effects.  
For more details on the application of Random Forests for exploratory analysis in social sciences, see Fife and D’Onofrio (2023).

### **2. Model Selection**
I identify the best model by starting with the most complex model that includes all non-linear relationships and interactions detected by Random Forests. I then iteratively reduce complexity by comparing the more complex models to simplified ones to find the best fit for the data.

### **3. Checking Assumptions**
I check the assumptions of logistic regression to ensure the model is valid and appropriate for the data. This verifies that the model allows for the interpretation of the estimates.

### **4. Bayesian Analysis for Validation**
I perform Bayesian analysis to validate the results obtained through logistic regression.

### **5. Replication with Bayesian Priors**
This step is "artificially" created to replicate the results using a Bayesian model, with the results of the previous analysis used as priors.  By "artificially" created, I mean that I divided the data set into an exploratory set and a confirmatory set. 
**Important Note:** This is an example of how Bayesian analysis can be used to integrate results from separate studies. This step is unnecessary if we have a single, large dataset. However, this analysis is intended to demonstrate how Bayesian methods could be applied in social sciences. You can think of this as a toy example and use it to compare the results of frequentist and Bayesian analyses. Since this step is confirmatory, I use the exact same model as in previous steps, without any changes.

### **6. Interpretation and Visualization**
Finally, I interpret the results and visualize them to make the findings more accessible and comprehensible.
**Important Note**: The interpretation of all effects assumes that all predictors act through a direct effect and do not operate indirectly through other predictors For a discussion on how interpretations change based on causal models, refer to Westreich & Greenland (2013).

# References

Fife, D. (2020). The Eight Steps of Data Analysis: A Graphical Framework to Promote Sound Statistical Analysis. Perspectives on Psychological Science, 15(4), 1054-1075. https://doi.org/10.1177/1745691620917333

Fife, D.A., D’Onofrio, J. Common, uncommon, and novel applications of random forest in psychological research. Behav Res 55, 2447–2466 (2023). https://doi.org/10.3758/s13428-022-01901-9

Hirschauer, N., Grüner, S., Mußhoff, O., Becker, C., & Jantsch, A. (2021). Inference using non-random samples? Stop right there!. Significance, 18(5), 20-24. https://doi.org/10.1111/1740-9713.01568

Westreich, D., & Greenland, S. (2013). The table 2 fallacy: presenting and interpreting confounder and modifier coefficients. American journal of epidemiology, 177(4), 292-298. https://doi.org/10.1093/aje/kws412

