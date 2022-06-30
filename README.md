# General Topics for Data Preprocessing

* Data Cleaning / cleasing
  - noisy data 
  - missing data analysis 
  - outlier analysis
  
* Data Standardization
  - 0-1 conversion 
  - convert to z score
  - logarithmic transformation
  
* Data Reduction
  - reducing the number of observations
  - reducing the number of variable
  
* Variable Transformations
  - transformation in continuous variables
  - transformation in categorical variables

## Data Cleaning

* Observations that are quite outside of the general trend in the data or that are quite different from other observations are called outliers.

* The numerical value that represents the separation is called the outlier.

* An observation unit with an outlier is called an outlier.

* Outliers mislead rule sets or functions created out of generalizability concerns. It causes bias.

* So how do we define going outside the general trend of the data set?

    1) Industry Information:
        - For example, not to include 1000 square meters of houses in a house price prediction model.

    2) Standard Deviation Approach:
        - It is added to the mean of a variable by calculating the standard deviation of the same variable. This value, which is obtained by adding 1,2 or 3 standard deviation values ​​to the mean, is considered the threshold value, and values ​​above or below this value are defined as outliers.
        - Threshold = Mean + 2 * Standard Deviation

    3) Z-Score Approach:
        - It works similarly to the standard deviation method. The variable is adapted to its standard normal distribution, that is, it is standardized. Then -for example- a threshold value is set according to the value of -+2.5 from the right and left of the distribution, and values ​​above or below this value are marked as outliers.

    4) Boxplot (interquartile range - IQR) Method:
        - It is one of the most commonly used methods. The value of the variable is sorted from least to greatest. A threshold value is calculated over the values ​​corresponding to their quarters (percentiles), namely Q1, Q3, and an outlier definition is made according to this threshold value.
        - (IQR = 1.5 * (Q3-Q1))
        - Lower threshold = Q1 -IQR
        - Upper threshold = Q3 + IQR


### Multivariate Outlier Analysis

#### Local Outlier Factor 

It allows us to identify values that may be outliers by scoring the observations based on the intensity at their location.

The local density of a point is compared with its neighbors. If a point is significantly lower than the density of its neighbors, it can be interpreted that this point is in a more sparse region than its neighbors. Therefore, there is a neighborhood structure here. If the perimeter of a value is not dense, then this value is considered as an outlier.

### Missing Data Anlaysis

It refers to the situation where there is a lack of observations in the examined and set.

If the observations with missing values are directly removed from the data set and their randomness is not examined, the reliability of the statistical inferences and modeling studies will decrease.

In order for the missing observations to be removed directly from the data set, the deficiency in the data set must have occurred completely by chance in some cases. If the deficiencies are caused by structural problems associated with the variables, then deletion operations may cause serious biases.

1. It is necessary to know whether the defect in the data set is structural or not.

2. NA does not always mean deficiency.

3. Loss of information.

#### Types Of Missing Data 

* Totally Random Loss: Observations that occur completely randomly, not caused by other variables or a structural problem.

* Random Loss: The type of deficiency that may occur depending on other variables.

* Non-Coincidental Loss: The type of deficiency that cannot be ignored and occurs with structural problems.

####  Test For Missing Data Randomness

* Visual Techniques
* Independent two-sample t-test
* Correlation test
* Little's MCAR test

#### How to Fix Missing Data Problem 

* Deletion Methods:
     - Observation or variable deletion method
     - List-based deletion method (Listwise Method)
     - Pairwise method
* Value Assignment Methods:
     - Median, mean, median
     - Assignment to the most similar unit (hot deck)
     - Outsourced assignment
* Predictive Methods:
     - Machine learning
     - EM
     - Multiple assignment method