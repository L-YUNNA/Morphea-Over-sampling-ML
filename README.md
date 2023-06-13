# Morphea-Over-sampling-ML

**Morphea (localized scleroderma)** is a rare disease characterized by hardening of the skin caused by the deposition of collagen and extracellular matrix due to chronic inflammation of the skin and subcutaneous tissue. (1) Systemic sclerosis (**SSc**) is an autoimmune disease characterized by vasculopathy, inflammation, and fibrosis of the skin and several internal organs. (2) SSc can lead to morbidity due to internal organ involvement; therefore, an early differential diagnosis between generalized morphea (**GM**) and SSc is necessary when extensive skin lesions are hardened. 
Our study aimed to describe the clinical and histopathological features of patients diagnosed with localized morphea (**LM**), GM, and SSc and identify the crucial elements for distinguishing each disease.
<br><br/>

## Dataset
**Our dataset is highly imbalanced** and it can be trained biased toward the majority class. To prevent this, we resampled the data using **Smote-Tomek** links method, which combines over- and under-sampling. 
| class | num of data |
|-------|----------------|
| LM    |       150      |
| GM    |        16      |
| SSc   |        15      |


**Smote-Tomek** links makes the class boundary clear and facilitate classification because it removes some of the majority class examples that have been invaded into the expanded minority class space by over-sampling. The result of visualizing after reducing the resampled data with k_neighbors parameter of 6 to two dimensions is shown in the eFigure 1 as below.<br><br/>
![image](https://github.com/L-YUNNA/Morphea-Over-sampling-ML/assets/129636660/1aaccac9-a8a9-4f6b-8947-c28fb39866ae)
<br><br/>


## Training
We chose the random forest algorithm. 
The dataset was divided into training and testing set in ratio of  7:3 and hyper-parameters were optimized by applying grid search algorithm and 3 fold cross validation. 
<br><br/>

## Performance
We calculated the **confusion matrix** to evaluate the performance on the testing set.

![image](https://github.com/L-YUNNA/Morphea-Over-sampling-ML/assets/129636660/799ffa7b-d285-48a6-8213-4c92a7506ded)
<br><br/>

Then, **SHAP** method was applied to Random Forest to make the output of the model interpretable. SHAP is based on the concept of Shapley value, which comes from coalitional game theory and is the average marginal contribution of one variable from all possible combinations of variables.

![image](https://github.com/L-YUNNA/Morphea-Over-sampling-ML/assets/129636660/d1ce8aef-683d-4978-907f-ec703a5dfcc9)
 <- GM figure
<br><br/>
