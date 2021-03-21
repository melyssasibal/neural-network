# Neural Network

## Project Overview

The purpose of this project is utilize machine learning and neural networks to classify if applicants would be successful given funding by Alphabet Soup. The dataset includes information on over 34,000 organization that have previously recevied funding from Alphabet Soup. Within this dataset, there are 12 variables, which will be further classified as features or targets or will be removed before fitting the model.    

## Results

**Data Preprocessing**

- What variable(s) are considered the target(s) for your model?
The target for the model is the variable "IS_SUCCESSFUL," which signifies whether a charity used their funding successfully. 

- What variable(s) are considered to be the features for your model?
The features for the model are: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT".

- What variable(s) are neither targets nor features, and should be removed from the input data?
"EIN" and "NAME" were not considered features or targets, and were removed from the input data. 


**Compiling, Training, and Evaluating the Model**

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
Initially, 80 neurons were selected. As provided in the module, a good starting point is 2-3 times the number of inputs for the hidden layer. The activation functions were chosen based on previous work in the module, as well. 

- Were you able to achieve the target model performance?
I was not able to achive the target model performance.

- What steps did you take to try and increase model performance?
For Attempt 1, I removed STATUS, SPECIAL CONSIDERATIONS and CLASSIFICATION from the features. Status and special considerations only have two unique values and therefore, it seems like those data offer little to the model. Additionally, classification has many unique values, which I thought may have been a source of confusion in the model. The accuracy of this attempt is lower than the initial model. 

![attempt1](/images/attempt1.png)

For Attempt 2, no features were removed, instead the number of neurons were increased and an additional hidden layer was added. Again, the accuracy of this attempt was slightly lower than the initial model.  

![attempt2](/images/attempt2.png)

For Attempt 3, the activvation functions for the hidden layers was changed to tanh. However, this did not increase the accuracy either. 

![attempt3](/images/attempt3.png)


## Summary

While there are a number of combinations of changes that could be incorporated into the model, the three attempts mentioned did not add to the model's accuracy. Recommendations to get more accurace predictions would be the following: 

- Add more data points: Alphabet Soup should incorporate criteria used to measure if an organization has been successful with their funding into this dataset. While neural networks are able to find patterns given any dataset, it may be possible this data is limited in providing a clearer picture. 

- Change income amount: Currently this variable is provided in income ranges for values. Maybe including the income from the previous fiscal year as a value, rather than range would be more beneficial. 

- Remove outliers: From a brief look at the dataset, there is a large range of ask amounts. While the data has been standardize for all attempts, it may be worthwhile to see if there are any extreme data points skewing the model. 