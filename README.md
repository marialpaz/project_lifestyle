# project_lifestyle

# Table of contents
1. [Introduction](#1-introduction)
2. [Dataset](#2-dataset)

## 1. Introduction
This project was developed using a dataset available in https://www.kaggle.com/datasets/ydalat/lifestyle-and-wellbeing-data?resource=download. The survey used to gather this data can be found in http://www.authentic-happiness.com/your-life-satisfaction-score and includes 24 attributes describing how we live our lives, including a calculated field, the WorkLifeBalance_Score. After exploring the data, it was built two different machine learning models in order to predict the body mass index from the lifestyle of the respondents.
### Project development

THe development of this project was done according with the following steps:
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
The dataset was split into train and test set with 70/30 ratio.There are 3 data types of data in the dataset: float64(5), int64(3) and object(3).  As shown in the image above, the dataset does not have NAN values.

## 3. Exploratory data analysis
<p align="center">
<img src="countplot-stress-gender.png" width="550" height="300"/>
</p>

From the plot above it seems more women are under lots of stress (3 0r more in the stress scale). In order to investigate that, let's look for each group separately (women and men) and see how much of each group declared to experience a lot of daily stress. 

<p align="center">
<img src="stress-percent.png" width="650" height="160"/>
</p>

By doing that, we can affirm that the proportion of men and women under much stress in both groups are not very different.

Another feature we explored was the "bmi_range" which is the body mass index and is represented by two classes: below 25 and above 25. First, let's see if they are balanced or not.

<p align="center">
<img src="bmi-balance.png" width="350" height="360"/>
</p>






## 4. Data preparation
## 5. Machine leaning modelling

[back to top](#table-of-contents)

---
