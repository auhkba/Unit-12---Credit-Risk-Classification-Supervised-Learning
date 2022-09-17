# Unit-12---Credit-Risk-Classification-Supervised-Learning

## Overview of the Analysis


* The purpose of the analysis. 

   >The purpose of the analysis is to accurately  identify any potential ***High-Risk Loans*** given a range of input variables.  



* Financial information, and what to predict.

    >There are 77,536 lines of lending data. Each line includes seven loan features, such as loan size, interest rate, etc,. 

    >The outcome of each line  is either labeled with the `0` (healthy loan) or `1` (high-risk loan) label. 

    >The whole data is split into a training set (75%) and a testing set(25%). The model is trained from a training set, and makes predictions (`0` or `1`) based on testing input data.


* Basic information about the variables

    >Target values consist of two classes, one is `0`, representing healthy loan, the other is `1` representing ‘high-risk loan’. The existing data have 75,036 with `0` which are healthy loans, 2,500 with `1` which are high risk loans.


* Stages of the machine learning process 

  1. Load the data from lending_data.csv;
  2. Split the data into training set and testing set by `train_test_split`;
  3. Train the model. Because we predict binary outcomes, either `0` or `1`, `LogistricRegression` is applied;
  4. Evaluate the model_1 performance with `testing set`;
  5. In training set, add additional random samples of the minority clase (`1` high-risk loan) until instances of minority eques instances of majority,  with `RandomOversampler`;
  6. Re-train the oversampled model with `LogistricRegression`;
  7. Evaluate the model_2 performance with `testing set`;
  8. Compare two models' performance according to the purpose of the Credit Risk Classification needs.




---

## Results

* Machine Learning Model 1:
  
  * Model Accuracy : 0.95
  * Healthy Loan:
    * Precision : 1.00
    * Recall : 0.99
  * High-Risk Loan:
    * Precision : 0.85
    * Recall : **0.91**


* Machine Learning Model 2:
  
  * Model Accuracy : 0.99
  * Healthy Loan:
    * Precision : 1.00
    * Recall : 0.99
  * High-Risk Loan:
    * Precision : 0.84
    * Recall : **0.99**

---
## Summary

Both models achieved very high accuracy scores, giving us a high confidence level that  the Classification model by using Logistic-Regression is able to classify healthy loans and high-risk loans.


Both models achieved very high precision and recall scores for `0` (Healthy loans). **However**, the purpose of prediction is to identify `1` (High-Risk loans), the loss of default loans will have substantial negative impact.

Therefore, a better model is required to achieve high **Recall Ratio** on `1` (High-Risk Loans) , which minimizes the **False Negative** numbers, and maximizes **True Positive** numbers. With a slight compromise of other ratios are acceptable , given that other scores are so high.

We recommend to use Model 2 -  a resampled logistic regression model to predict creditworthiness of borrowers.
