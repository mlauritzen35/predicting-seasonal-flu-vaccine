# w207-sec03-bhat-hejazi-huang-lauritzen
## Team Members: Tajesvi Bhat, Emily Huang, Yasmine Hejazi, Matt Lauritzen

### Introduction
A vaccine for the H1N1 flu virus became publicly available in October 2009. In late 2009 and early 2010, the United States conducted the National 2009 H1N1 Flu Survey. This phone survey asked respondents whether they had received the H1N1 and seasonal flu vaccines, in conjunction with questions about themselves. These additional questions covered their social, economic, and demographic background, opinions on risks of illness and vaccine effectiveness, and behaviors towards mitigating transmission. A better understanding of how these characteristics are associated with personal vaccination patterns can provide guidance for future public health efforts.

This project was inspired by an existing competition by Driven Data, [Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines](https://www.drivendata.org/competitions/66/flu-shot-learning/page/210/). The data is provided courtesy of the United States National Center for Health Statistics and is the National 2009 H1N1 Flu Survey (NHFS). Each row in the dataset represents one person who responded to the National 2009 H1N1 Flu Survey. The dataset includes 35 features.

For this competition, there are two target variables:

- h1n1_vaccine - Whether respondent received H1N1 flu vaccine.
- seasonal_vaccine - Whether respondent received seasonal flu vaccine.
Both are binary variables: 0 = No; 1 = Yes. Some respondents didn't get either vaccine, others got only one, and some got both. This is formulated as a multilabel (and not multiclass) problem.

In this project, our goal is to predict how likely individuals are to receive their H1N1 and seasonal flu vaccines. Specifically, we'll be predicting two probabilities: one for h1n1_vaccine and one for seasonal_vaccine.

### Code Breakdown:
We chose to run a total of 3 models (2 Logistic Regression, 1 Random Forest) that are available in the following files: lr_model_1.ipynb, lr_model_2.ipynb, and rf_model.ipynb. 

- baseline_model.ipynb houses the code for the baseline model with a focus on the top 10 correlated features
- lr_model_1.ipynb is the first logistic regression with top 10 correlated numerical features and limited feature engineering
- lr_model_2.ipynb is the second logistic regression iteration with all numeric features from the dataset. This model gave us the highest accuracy of 82.7%
- rf_model.ipynb is a Random Forest with top 28 important features (feature importance > 0.01) and hyperparameter tuning performed for numTrees and maxDepth

The model_iterations directory contains our experiments such as the alternative models we tried and their results.

The Data file contains: 
- training_set_features.csv, the set of features for the training data set
- training_set_labels. csv, the provided set of labels for the training data set
- test_set_features.csv, the provided set of features for the test data set

Because this project was part of a competition, we were not provided with the test_set_labels.

### Conclusion:
Key Results:
- The best model accuracy was obtained from our Logistic Regression Model that took into account all numeric features of the dataset.
- Some numerical features that we did not originally consider ended up being important (ex. Age 65+ years)

What we Learned:
- Predicting something as complex as user behavior particularly when it comes to vaccines is incredibly difficult. We’ve learned that there are many facets and nuances and many features end up being important.
- Data quality is as important as algorithm quality!
- There are certain difficulties  with implementing certain packages, especially as the field grows and computers/tech grows as well, that cannot always be accounted for.

Avenues for future work:
- We primarily focused on predictions for seasonal_vaccine, but the dataset has information on the H1N1 vaccine as well. The next step would be to apply our models to predict H1N1 vaccination likelihoods
- We could increase the number of respondents and records which would increase the total size of the dataset and improve our results
The dataset is from 2009. Future work could involve collecting data from 2009-now and perform time series analysis, or compare this model’s performance on 2009 data with data from 2022.
- There were quite a few missing values (especially in variable health_insurance) that we ultimately dropped from the dataset. This resulted in over 12000 records being dropped. Future work could delve into how best to handle the aforementioned situation and observe how that impacted results
- How can this be misused? With the increased relevance and growth of the Anti-Vacc movement, can such models be used against Anti-Vaccers or vice versa?


### Contributions:
All four group members were essential to the implementation, execution and completion of this project. The individual contribution breakdown is as follows:
- Tajesvi: data processing, algorithm implementation, experiments, presentation
- Emily: data processing, algorithm implementation, experiments, presentation
- Yasmine: data processing, algorithm implementation, experiments, presentation. Ultimately chose the Random Forest model Yasmine created.
- Matt: data processing, algorithm implementation, experiments, presentation. Ultimately chose the Logistic Regression model Matt created.
