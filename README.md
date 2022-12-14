# project_lifestyle

# Table of contents
1. [Introduction](#1-introduction)
2. [Dataset](#2-dataset)
3. [Exploratory data analysis](#3-exploratory-data-analysis)
4. [Data preparation](#4-data-preparation)
5. [Machine learning modelling](#5-machine-learning-modelling)
     * [5.1 Models and performance](#51--models-and-performance)

## 1. Introduction
This project was developed using a dataset available in https://www.kaggle.com/datasets/ydalat/lifestyle-and-wellbeing-data?resource=download. The survey used to gather this data can be found in http://www.authentic-happiness.com/your-life-satisfaction-score and includes 24 attributes describing how we live our lives, including a calculated field, the WorkLifeBalance_Score. After exploring the data, it was built two different machine learning models in order to predict the "bmi-range" (body mass index) from the lifestyle of the respondents.
### Project development

The development of this project was done according with the following steps:
- Exploratory Data Analysis 
- Data Preparation
- Machine Learning Modelling and Tuning
- Model Evaluation

## 2. Dataset
The dataset has 15971 entries and 24 features described below:


**Timestamp** - Date when survey was submitted.


**FRUITS_VEGGIES** - HOW MANY FRUITS OR VEGETABLES DO YOU EAT EVERYDAY?


**DAILY_STRESS** - HOW MUCH STRESS DO YOU TYPICALLY EXPERIENCE EVERYDAY?


**PLACES_VISITED** - HOW MANY NEW PLACES DO YOU VISIT? * Over a period of 12 months.


**CORE_CIRCLE** - HOW MANY PEOPLE ARE VERY CLOSE TO YOU? * i.e. close family and friends ready to provide you with a long-term unconditional support.


**SUPPORTING_OTHERS** - HOW MANY PEOPLE DO YOU HELP ACHIEVE A BETTER LIFE?


**SOCIAL_NETWORK** - WITH HOW MANY PEOPLE DO YOU INTERACT WITH DURING A TYPICAL DAY? 


**ACHIEVEMENT** - HOW MANY REMARKABLE ACHIEVEMENTS ARE YOU PROUD OF? * Over the last 12 months.


**DONATION** - HOW MANY TIMES DO YOU DONATE YOUR TIME OR MONEY TO GOOD CAUSES? * Over a period of 12 months. 


**BMI_RANGE** - WHAT IS YOUR BODY MASS INDEX (BMI) RANGE?


**TODO_COMPLETED** - HOW WELL DO YOU COMPLETE YOUR WEEKLY TO-DO LISTS?


**FLOW** - IN A TYPICAL DAY, HOW MANY HOURS DO YOU EXPERIENCE "FLOW"? Flow is defined as the mental state, in which you are fully immersed in performing an activity.


**DAILY_STEPS** - HOW MANY STEPS (IN THOUSANDS) DO YOU TYPICALLY WALK EVERYDAY?


**LIVE_VISION**  -  FOR HOW MANY YEARS AHEAD IS YOUR LIFE VISION VERY CLEAR FOR? 


**SLEEP_HOURS** - ABOUT HOW LONG DO YOU TYPICALLY SLEEP?


**LOST_VACATION** - HOW MANY DAYS OF VACATION DO YOU TYPICALLY LOSE EVERY YEAR?


**DAILY_SHOUTING** - HOW OFTEN DO YOU SHOUT OR SULK AT SOMEBODY? * In a typical week.


**SUFFICIENT_INCOME** - HOW SUFFICIENT IS YOUR INCOME TO COVER BASIC LIFE EXPENSES?


**PERSONAL_AWARDS** - HOW MANY RECOGNITIONS HAVE YOU RECEIVED IN YOUR LIFE? 


**TIME_FOR_PASSION** - HOW MANY HOURS DO YOU SPEND EVERYDAY DOING WHAT YOU ARE PASSIONATE ABOUT? 


**WEEKLY_MEDITATION** - IN A TYPICAL WEEK, HOW MANY TIMES DO YOU HAVE THE OPPORTUNITY TO THINK ABOUT YOURSELF?


**AGE** - YOUR AGE RANGE.


**GENDER** - YOUR GENDER.


**WORK_LIFE_BALANCE_SCORE** - CALCULATED SCORE.

When loaded in pandas this dataset file has a memory usage of 2.9 MB.

<p align="center">
<img src="info-lifestyle.png" width="550" height="450"/>
</p>
The dataset was split into train and test set with 70/30 ratio.There are 3 types of data in the dataset: float64(5), int64(3) and object(3).  As shown in the image above, the dataset does not have NAN values.

## 3. Exploratory data analysis

In this section it was explored the available information in order to get to know the data and decide what to investigate deeper. The first feature we looked into was the "daily_stress".

<p align="center">
<img src="countplot-stress-gender.png" width="540" height="320"/>
</p>

From the plot above it seems more women are under lots of stress (3 0r more in the stress scale). In order to investigate that, it was treated each group separately (women and men) to see how much of each group declared to experience a lot of daily stress. 

<p align="center">
<img src="stress-percent.png" width="870" height="180"/>
</p>

By doing that, we can affirm that the proportion of men and women under much stress in both groups are not very different.

Another feature explored was the "bmi_range" which is the body mass index and is represented by two classes: below 25 and above 25. First, let's see if they are balanced or not.

<p align="center">
<img src="bmi-balance.png" width="360" height="380"/>
</p>

Even thought most declared to belong to class 1 (below 25), there is not a high imbalance between them.




## 4. Data preparation

Aiming to run a machine learning for this dataset, some data preparation was needed. For example, the columns "daily_stress", "todo_completed", "sufficient_income", "age" and  "gender" are categorical features, thus they were turned into dummy variables.

<p align="center">
<img src="dummies.png" width="875" height="60"/>
</p>

 Once there were not nan or missing values, the dataset was ready for a machine learning model. The timestamp column was dropped once in our problem this information did not show much importance.

After exploring our dataset, the quantity taken as the target was the "bmi_range". Therefore, based on the other features, it was predicted if someone has a body mass index below or above 25 from their lifestyle.

<p align="center">
<img src="target.png" width="850" height="40"/>
</p>

For the features, we considered all features from our dataset,  except "bmi_range" and "work_life_balance_score". This last one had to be dropped, once it is a calculated field from the answers of the respondents and it takes into account all the other features including "bmi_range".

<p align="center">
<img src="features.png" width="850" height="50"/>
</p>

### Spliting the data
The next step was to split the data into train and test sets.

<p align="center">
<img src="splitting.png" width="850" height="215"/>
</p>

After the steps above, all data is ready to be used a machine learning model. 

## 5. Machine learning modelling

### 5.1.  Models and performance

The following machine learning models were considered to predict the "bmi-range" of the respondents.
* Random Forest
* Logistic Regression

The performance of the models were evaluated by the classification_report and confusion matrix, both of them imported from sklearn.metrics.
### Random Forest

#### Classification report
<p align="center">
<img src="CR-random forest.png" width="850" height="185"/>
</p>

#### confusion matrix 

<p align="center">
<img src="cm-random forest.png" width="850" height="300"/>
</p>

### Logistic Regression 

#### Classification report
<p align="center">
<img src="cr-logistic.png" width="850" height="185"/>
</p>

#### confusion matrix 

<p align="center">
<img src="cm-logistic.png" width="850" height="300"/>
</p>

Even though both models did not present a very good accuracy, the Random Forest has slightly better metrics for class 1 (below 25) and 2 (above 25). The LR as well as the RF model are predicting many cases belonging class 1 (below 25) when the true label is in fact class 2 (above 25). To make sure that the model was certain that a case belonged to class 1, we guaranteed that it was only predicting that an example belonged to this class when the probability was equal or above 0,58 (58%), which represents the percentage of respondents who declared to belong to class 1.

#### Increasing threshold - 58%

<p align="center">
<img src="prob-58.png" width="850" height="175"/>
</p>

<p align="center">
<img src="cr-threshold.png" width="850" height="185"/>
</p>


<p align="center">
<img src="cm-threshold.png" width="850" height="300"/>
</p>


By making the model only predicting an example as belonging to class 1 when the probability was higher than 0,58 (58 %) did not increase the accuracy, but on the other hand the true positive - TP and true negative - TN classes are much better predicted by the model, as a consequence the other metrics for class 2 were much improved.


Another possibility to optimize the Logistic Regression model proposed here is to use GridSearchCV for hyper-parameters tuning.

#### Hyper-parameters tuning 

Hyper-parameters are parameters not directly learnt within a estimator, which in this case is the LogisticRegression(). In scikit-learn they are passed as arguments to the constructor of the estimator classes.

In scikit-learn there are two generic approaches to search the best parameters: for given values, GridSearchCV exhaustively considers all parameter combinations, while RandomizedSearchCV can sample a given number of candidates from a parameter space with a specified distribution. Here, we decided to use the GridSearchCV approach.

<p align="center">
<img src="gridsearching1.png" width="850" height="150"/>
</p>

The grid search provided by GridSearchCV generates candidates from a grid of parameter values specified with the param_grid parameter.

<p align="center">
<img src="gridsearch.png" width="850" height="110"/>
</p>

After this process, we have the best parameters for a better performance of the model. However, even by doing that the accuracy of the logistic regression model did not increase.

<p align="center">
<img src="gridsearchingcv.png" width="850" height="100"/>
</p>


[back to top](#table-of-contents)

---
