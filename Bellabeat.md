# **Bellabeat Case Stuty**

Thu Hang Tranova
<br>
<br>

This case study is part of the [Google Data Analytics Professional Certificate](https://www.coursera.org/google-certificates/data-analytics-certificate?network=g&utm_source=gg&adposition=&creativeid=658353603310&matchtype=&adgroupid=148629173669&gclid=CjwKCAjw_aemBhBLEiwAT98FMmeL05UFV56kyUe4XA3sbz6KqHoqojgSqRZladBghJbgy7WQTvWpvRoCiXsQAvD_BwE&keyword=&hide_mobile_promo=&utm_campaign=B2C_EMEA_google-data-analytics_google_FTCOF_google-certificates_country-GB&campaignid=20120837007&devicemodel=&utm_medium=sem&device=c&redirected_from_description_page=true). It will focus on Bellabeat, a wellness brand for women, and provide analysis on smart device usage to inform and refine its marketing strategy. To achieve this the data analysis process will be followed: **ask**, **prepare**, **process**, **analyse**, **share**, and **act**. RStudio, a programming tool built for R, will be employed to clean, analyse and visualise the data. 

<div style="width:100%;text-align: center;"> <img src="https://api.time.com/wp-content/uploads/2022/11/best-inventions-2022-bellabeat-ivy.jpg?quality=85&w=715" width="500"/>
     </div>
<div style="text-align: center;">
 <em>Bellabeat Ivy (2022) Available at:https://time.com/collection/best-inventions-2022/6228846/bellabeat-ivy/</em>
    </div>

## Table of Contents
* [The Company: Bellabeat](#company)
* [Section 1: Ask](#section-one)
    * [1.1 Business Task](#business-task)
    * [1.2 Key Stakeholders](#key-stakeholders)
* [Section 2: Prepare](#section-two)
    * [2.1 Data Source and Data Organisation](#data-source-and-data-organisation)
    * [2.2 Data Licensing and Privacy](#data-licensing-and-privacy)
    * [2.3 ROCCC Analysis](#ROCCC-analysis)
    * [2.4 Limitations](#limitations)
* [Section 3: Process](#section-three)
    * [3.1 Installing and Loading Packages](#installing-and-loading-packages)
    * [3.2 Importing Datasets and Assigning New Names](#importing-datasets-and-assigning-new-names)
    * [3.3 Exploring the Datasets](#exploring-the-datasets)
    * [3.4 Data Cleaning](#data-cleaning)
    * [3.5 Adding 'weekday' Column](#adding-weekday-column)
    * [3.6 Merging Datasets](#merging-datasets)
    * [3.7 Summary of the Datasets](#summary-of-the-datasets)
* [Section 4: Analyse and Share](#section-four)
    * [4.1 Summary Statistics](#summary-statistics)
    * [4.2 Main Topics](#main-topics)
* [Section 5: Act](#section-five)
    * [5.1 Smart Device Usage Trends](#smart-device-usage-trends)
    * [5.2 Applying the Trends to Bellabeat Customers](#applying-the-trends-to-bellabeat-customers)
    * [5.3 Bellabeat Marketing Strategy Recommendations](#bellebeat-marketing-strategy-recs)
* [Conclusion](#selection-conclusion)

<a id="company"></a>
# The Company: Bellabeat
Bellabeat is a wellness brand providing high-tech products and services designed to help women adopt healthier lifestyles.

Bellabeat was founded by Urška Sršen and Sando Mur in 2013 and has grown rapidly over the years. The company has extensively invested in both traditional and digital marketing, including Google search engines and maintaining an active social media presence. Despite its successes, Bellabeat recognizes the potential for further growth. Therefore, an in-depth analysis of consumer data from a different brand will be conducted to inform Bellabeat's marketing strategy and potentially enhance its existing products and features.

## Products
* **Bellabeat App** - Provides users with health data related to their activity, sleep, stress, menstrual cycle, and mindfulness habits, allowing users to understand their habits better and make healthier decisions.
* **Bellabeat Membership** - Offers users 24/7 access to personalized guidance on nutrition, activity, sleep, health and beauty, and mindfulness tailored to their lifestyle and goals.
* **Leaf** - A wearable wellness tracker available as a bracelet, necklace, or clip. It can track activity, sleep, and stress levels while also sending reminders to stay active.
* **Spring** - A smart water bottle tracking daily water intake.
* **Time** - A luxury wellness watch equipped with smart technology to monitor user’s activity, sleep, and stress levels, providing insight into users’ daily lifestyle and progress while sending reminders to stay active. Its elegant design makes the watch suitable for any occasion.
* **Ivy** - A health tracker in the form of an elegant bracelet, monitoring not only activity, sleep, and stress but also heart rate, respiratory rate, cardiac coherence, and physical and mental activity.

## Target Audience
### Key Demographics
* **Age:** [19 - 40](https://www.wework.com/ideas/community-stories/member-spotlight/bellabeat-chic-fitness-tracker-looks-like-jewelry-keeps-women-healthy); women in various life stages, from puberty to menopause
* **Gender:** Female
* **Location:** Primarily the USA, with additional markets in Europe, Asia, and the Middle East
* **Socio-economic Status:** Middle and upper-class working professionals

### Key Psychographics
* They have a **holistic view of health** by caring for the whole person - the physical, mental, spiritual, and social well-being.
* They are **health-conscious**, prioritising healthy dietary choices.
* They **tend to invest considerable money on health care and wellness**.
### Challenges and Needs
* **Limited time for daily workouts** due to typical 5-day workweeks.
* Desire for fitness trackers that are **functional, sleek, and stylish, suitable for any occasion**. 
<br>
<br>

<a id="section-one"></a>
# Section 1: Ask
In this section, the problem to be solved will be defined.

<a id="business-task"></a>
## 1.1 Business Task
Bellabeat aims to identify potential growth opportunities by analyzing smart device usage data to understand how consumers use **non-Bellabeat** smart devices. Insights gained will guide Bellabeat's marketing strategy and inspire new ideas for their existing products and services.

This case study will focus on improving one of Bellabeat's products - **Ivy, the wellness and health tracker**. 

### Questions to Consider
1. What are the current trends in smart device usage?
2. How do these trends relate to Bellabeat's target customers?
3. How can these trends influence Bellabeat's marketing strategy?

<a id="key-stakeholders"></a>
## 1.2 Key Stakeholders
* **Urška Sršen** - Co-founder and Chief Creative Officer of Bellabeat
* **Sando Mur** - Co-founder and member of Bellabeat's executive team
* **Bellabeat Marketing Analytics Team**
<br>
<br>

<a id="section-two"></a>
# Section 2: Prepare
In this section, useful and relevant data for solving the business task will be identified.

<a id="data-source-and-data-organisation"></a>
## 2.1 Data Source and Data Organisation
For this case study, the [FitBit Fitness Tracker Data](https://www.kaggle.com/arashnic/fitbit) will be used. The dataset is publicly available on Kaggle. The dataset was collected through a survey via Amazon Mechanical Turk **between March 12, 2016, and May 12, 2016**. It contains personal tracker data from **30 Fitbit users**, who consented to submit minute-level output for physical activity, heart rate, and sleep monitoring. This includes information on daily activity, steps, and heart rate, revealing patterns in users' habits. The dataset is organized into 18 CSV files in both long and wide formats.

<a id="data-licensing-and-privacy"></a>
## 2.2 Data Licensing and Privacy
The dataset is published by Möbius under the CC0: Public Domain Creative License, allowing free use without requiring permission from the copyright owner. Therefore, no licensing for the dataset is needed for this analysis.

Participants provided consent for the submission of personal tracker data, and their identities were anonymized using ID numbers instead of real names to ensure participant confidentiality.

<a id="ROCCC-analysis"></a>
## 2.3 ROCCC Analysis
To evaluate if the data source is credible and trustworthy, the ROCCC analysis will be employed.

**R**eliable: **Low**
* The dataset includes only 30 participants, which may not adequately represent Fitbit's user base, which is more than [31 million in 2020](https://www.statista.com/statistics/472600/fitbit-active-users/). While the sample size is small, according to the Central Limit Theorem (CLT), the sample of 30 is the smallest size that is still considered valid. However, a larger sample size would still be recommended to increase the confidence level of the research.
* The survey was conducted over two months, from 03/12/2016 to 05/12/2016, but the data only shows one month of activity from 04/12/2016 to 05/12/2016. While some people might have daily fitness routines, many people might adjust their fitness routine throughout the seasons. One month of data might not reflect that adjustment. A longer timeframe, spanning a full year, would offer more comprehensive insights.
* Amazon Mechanical Turk is known to [resemble the US population](https://researchmethodscommunity.sagepub.com/blog/who-can-i-sample-on-amazon-mechanical-turk) fairly well, relevant to this study as Bellabeat's customers are predominantly Americans.

**O**riginal: **Low**
* Third-party data from Amazon Mechanical Turk was used. While this company is commonly used for behavioral research, direct data from Fitbit would bolster reliability.

**C**omprehensive: **Medium**
* The dataset includes information about activity, sleep, steps, and heart rate, relevant to understanding smart device usage trends.
* Bellabeat's target market is women. Therefore, data related specifically to women's health and activity would be beneficial to find trends that could be applied to Bellabeat's customers.
* The dataset focuses solely on Fitbit data. However, there are many other fitness smart device companies with different functionalities and services, which could provide additional insights.

**C**urrent: **Low**
* The study was conducted in 2016, which was 7 years ago. Since then, [fitness trends have evolved significantly](https://journals.lww.com/acsm-healthfitness/fulltext/2022/01000/worldwide_survey_of_fitness_trends_for_2022.6.aspx), especially after Covid-19. For instance, outdoor activities surged in popularity, and home exercise gyms became more prevalent, trends that were not prominent in 2016.
* Wearable fitness technology was the no.1 trend in both 2016 and 2022. However, during that period, health and fitness technology have developed immensely, with many new services and functions being provided.
* These changes may decrease the usefulness and relevance of the data, potentially rendering it insufficient for current analysis.

**C**ited: **High**
* The data is cited with sources being documented.
* Data was collected by a third-party company, Amazon Mechanical Turk, made available through Möbius.
* The dataset was last updated 3 years ago.

<a id="limitations"></a>
## 2.4 Limitations
* **No demographic characteristics** about the participants were collected, such as their gender, age, location, and lifestyle. Without this information, it's challenging to determine if the dataset accurately represents Bellabeat's target audience.
* It is also **unknown how the data was collected**. Whether random sampling or purposive sampling was utilized.
<br>
<br>

<a id="section-three"></a>
# Section 3: Process
In this section, the selected data will be cleaned to ensure it is complete and free of errors and outliers. RStudio will be used to explore, analyze, and visualize the data.

<a id="installing-and-loading-packages"></a>
## 3.1 Installing and Loading Packages
First, key packages for the analysis will be installed and then loaded to use their functionalities.

```r
# Loading libraries
library("tidyverse")
library("dplyr")
library("readr")
library("janitor")
library("ggplot2")
library("lubridate")
library("skimr")
library("gridExtra")
```

<a id="importing-datasets-and-assigning-new-names"></a>
## 3.2 Importing Datasets and Assigning New Names
Before importing the datasets, it is important to verify if they are in the current working directory. If not, the `setwd()` function will be utilised to change this. Following that, the datasets will be imported, and new names will be assigned to facilitate identification.

```r
# Importing datasets and assigning new names
daily_activity <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/dailyActivity_merged.csv")
daily_calories <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/dailyCalories_merged.csv")
daily_intensities <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/dailyIntensities_merged.csv")
daily_steps <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/dailySteps_merged.csv")
daily_sleep <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/sleepDay_merged.csv")
heartrate_seconds <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/heartrate_seconds_merged.csv")
hourly_calories <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/hourlyCalories_merged.csv")
hourly_intensities <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/hourlyIntensities_merged.csv")
hourly_steps <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/hourlySteps_merged.csv")
minute_calories_narrow <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteCaloriesNarrow_merged.csv")
minute_calories_wide <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteCaloriesWide_merged.csv")
minute_intensities_narrow <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteIntensitiesNarrow_merged.csv")
minute_intensities_wide <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteIntensitiesWide_merged.csv")
minute_METs_narrow <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteMETsNarrow_merged.csv")
minute_sleep <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteSleep_merged.csv")
minute_steps_narrow <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteStepsNarrow_merged.csv")
minute_steps_wide <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/minuteStepsWide_merged.csv")
weight_log_info <- read_csv("/kaggle/input/fitbit/mturkfitbit_export_4.12.16-5.12.16/Fitabase Data 4.12.16-5.12.16/weightLogInfo_merged.csv")
```
<a id="exploring-the-datasets"></a>
## 3.3 Exploring the Datasets
To get a quick idea of what is in the datasets, the `glimpse()` function will be used. The datasets will be divided into daily, hourly, minute, and second dataframes.

***Daily DataFrames***
```r
# A quick preview of Daily Datasets
print("-----Daily Activity-----")
glimpse(daily_activity)

print("-----Daily Calories-----")
glimpse(daily_calories)

print("-----Daily Intensities-----")
glimpse(daily_intensities)

print("-----Daily Steps-----")
glimpse(daily_steps)

print("-----Daily Sleep-----")
glimpse(daily_sleep)

print("-----Weight Log Info-----")
glimpse(weight_log_info)
```

```{r, results='markup'}
[1] "-----Daily Activity-----"
Rows: 940
Columns: 15
$ Id                       <dbl> 1503960366, 1503960366, 1503960366, 150396036…
$ ActivityDate             <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/…
$ TotalSteps               <dbl> 13162, 10735, 10460, 9762, 12669, 9705, 13019…
$ TotalDistance            <dbl> 8.50, 6.97, 6.74, 6.28, 8.16, 6.48, 8.59, 9.8…
$ TrackerDistance          <dbl> 8.50, 6.97, 6.74, 6.28, 8.16, 6.48, 8.59, 9.8…
$ LoggedActivitiesDistance <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
$ VeryActiveDistance       <dbl> 1.88, 1.57, 2.44, 2.14, 2.71, 3.19, 3.25, 3.5…
$ ModeratelyActiveDistance <dbl> 0.55, 0.69, 0.40, 1.26, 0.41, 0.78, 0.64, 1.3…
$ LightActiveDistance      <dbl> 6.06, 4.71, 3.91, 2.83, 5.04, 2.51, 4.71, 5.0…
$ SedentaryActiveDistance  <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
$ VeryActiveMinutes        <dbl> 25, 21, 30, 29, 36, 38, 42, 50, 28, 19, 66, 4…
$ FairlyActiveMinutes      <dbl> 13, 19, 11, 34, 10, 20, 16, 31, 12, 8, 27, 21…
$ LightlyActiveMinutes     <dbl> 328, 217, 181, 209, 221, 164, 233, 264, 205, …
$ SedentaryMinutes         <dbl> 728, 776, 1218, 726, 773, 539, 1149, 775, 818…
$ Calories                 <dbl> 1985, 1797, 1776, 1745, 1863, 1728, 1921, 203…
[1] "-----Daily Calories-----"
Rows: 940
Columns: 3
$ Id          <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960366…
$ ActivityDay <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/2016", "4/16/…
$ Calories    <dbl> 1985, 1797, 1776, 1745, 1863, 1728, 1921, 2035, 1786, 1775…
[1] "-----Daily Intensities-----"
Rows: 940
Columns: 10
$ Id                       <dbl> 1503960366, 1503960366, 1503960366, 150396036…
$ ActivityDay              <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/…
$ SedentaryMinutes         <dbl> 728, 776, 1218, 726, 773, 539, 1149, 775, 818…
$ LightlyActiveMinutes     <dbl> 328, 217, 181, 209, 221, 164, 233, 264, 205, …
$ FairlyActiveMinutes      <dbl> 13, 19, 11, 34, 10, 20, 16, 31, 12, 8, 27, 21…
$ VeryActiveMinutes        <dbl> 25, 21, 30, 29, 36, 38, 42, 50, 28, 19, 66, 4…
$ SedentaryActiveDistance  <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …
$ LightActiveDistance      <dbl> 6.06, 4.71, 3.91, 2.83, 5.04, 2.51, 4.71, 5.0…
$ ModeratelyActiveDistance <dbl> 0.55, 0.69, 0.40, 1.26, 0.41, 0.78, 0.64, 1.3…
$ VeryActiveDistance       <dbl> 1.88, 1.57, 2.44, 2.14, 2.71, 3.19, 3.25, 3.5…
[1] "-----Daily Steps-----"
Rows: 940
Columns: 3
$ Id          <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960366…
$ ActivityDay <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/2016", "4/16/…
$ StepTotal   <dbl> 13162, 10735, 10460, 9762, 12669, 9705, 13019, 15506, 1054…
[1] "-----Daily Sleep-----"
Rows: 413
Columns: 5
$ Id                 <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 150…
$ SleepDay           <chr> "4/12/2016 12:00:00 AM", "4/13/2016 12:00:00 AM", "…
$ TotalSleepRecords  <dbl> 1, 2, 1, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, …
$ TotalMinutesAsleep <dbl> 327, 384, 412, 340, 700, 304, 360, 325, 361, 430, 2…
$ TotalTimeInBed     <dbl> 346, 407, 442, 367, 712, 320, 377, 364, 384, 449, 3…
[1] "-----Weight Log Info-----"
Rows: 67
Columns: 8
$ Id             <dbl> 1503960366, 1503960366, 1927972279, 2873212765, 2873212…
$ Date           <chr> "5/2/2016 11:59:59 PM", "5/3/2016 11:59:59 PM", "4/13/2…
$ WeightKg       <dbl> 52.6, 52.6, 133.5, 56.7, 57.3, 72.4, 72.3, 69.7, 70.3, …
$ WeightPounds   <dbl> 115.9631, 115.9631, 294.3171, 125.0021, 126.3249, 159.6…
$ Fat            <dbl> 22, NA, NA, NA, NA, 25, NA, NA, NA, NA, NA, NA, NA, NA,…
$ BMI            <dbl> 22.65, 22.65, 47.54, 21.45, 21.69, 27.45, 27.38, 27.25,…
$ IsManualReport <lgl> TRUE, TRUE, FALSE, TRUE, TRUE, TRUE, TRUE, TRUE, TRUE, …
$ LogId          <dbl> 1.462234e+12, 1.462320e+12, 1.460510e+12, 1.461283e+12,…
```
***Hourly DataFrames***
```r
# A quick preview of Hourly Datasets
print("-----Hourly Calories-----")
glimpse(hourly_calories)

print("-----Hourly Intensities-----")
glimpse(hourly_intensities)

print("-----Hourly Steps-----")
glimpse(hourly_steps)
```
```{r, results='markup'}
[1] "-----Hourly Calories-----"
Rows: 22,099
Columns: 3
$ Id           <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 150396036…
$ ActivityHour <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", "4/12/20…
$ Calories     <dbl> 81, 61, 59, 47, 48, 48, 48, 47, 68, 141, 99, 76, 73, 66, …
[1] "-----Hourly Intensities-----"
Rows: 22,099
Columns: 4
$ Id               <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 15039…
$ ActivityHour     <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", "4/1…
$ TotalIntensity   <dbl> 20, 8, 7, 0, 0, 0, 0, 0, 13, 30, 29, 12, 11, 6, 36, 5…
$ AverageIntensity <dbl> 0.333333, 0.133333, 0.116667, 0.000000, 0.000000, 0.0…
[1] "-----Hourly Steps-----"
Rows: 22,099
Columns: 3
$ Id           <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 150396036…
$ ActivityHour <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", "4/12/20…
$ StepTotal    <dbl> 373, 160, 151, 0, 0, 0, 0, 0, 250, 1864, 676, 360, 253, 2…
```
***Minute DataFrames***
```r
# A quick preview of Minute Datasets
print("-----Minute Calories-----")
glimpse(minute_calories_narrow)

print("-----Minute Intensities-----")
glimpse(minute_intensities_narrow)

print("-----Minute METs-----")
glimpse(minute_METs_narrow)

print("-----Minute Sleep-----")
glimpse(minute_sleep)

print("-----Minute Steps-----")
glimpse(minute_steps_narrow)
```
```{r, results='markup'}
[1] "-----Minute Calories-----"
Rows: 1,325,580
Columns: 3
$ Id             <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960…
$ ActivityMinute <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM", "4/12…
$ Calories       <dbl> 0.7865, 0.7865, 0.7865, 0.7865, 0.7865, 0.9438, 0.9438,…
[1] "-----Minute Intensities-----"
Rows: 1,325,580
Columns: 3
$ Id             <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960…
$ ActivityMinute <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM", "4/12…
$ Intensity      <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
[1] "-----Minute METs-----"
Rows: 1,325,580
Columns: 3
$ Id             <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960…
$ ActivityMinute <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM", "4/12…
$ METs           <dbl> 10, 10, 10, 10, 10, 12, 12, 12, 12, 12, 12, 12, 10, 10,…
[1] "-----Minute Sleep-----"
Rows: 188,521
Columns: 4
$ Id    <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960366, 1503…
$ date  <chr> "4/12/2016 2:47:30 AM", "4/12/2016 2:48:30 AM", "4/12/2016 2:49:…
$ value <dbl> 3, 2, 1, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3, 2, 1, 1, 1, 1, 1, 1…
$ logId <dbl> 11380564589, 11380564589, 11380564589, 11380564589, 11380564589,…
[1] "-----Minute Steps-----"
Rows: 1,325,580
Columns: 3
$ Id             <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503960…
$ ActivityMinute <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM", "4/12…
$ Steps          <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
```
***Second DataFrame***
```r
# A quick preview of Second Datasets
print("-----Heartrate Seconds-----")
glimpse(heartrate_seconds)
```
```{r, results='markup'}
[1] "-----Heartrate Seconds-----"
Rows: 2,483,658
Columns: 3
$ Id    <dbl> 2022484408, 2022484408, 2022484408, 2022484408, 2022484408, 2022…
$ Time  <chr> "4/12/2016 7:21:00 AM", "4/12/2016 7:21:05 AM", "4/12/2016 7:21:…
$ Value <dbl> 97, 102, 105, 103, 101, 95, 91, 93, 94, 93, 92, 89, 83, 61, 60, …
```
<a id="data-cleaning"></a>
## 3.4 Data Cleaning
Following the exploration of the datasets, several issues have been identified necessitating data cleaning actions to ensure data integrity and prepare the data for analysis.

### 3.4.1 Naming Conventions and Date Variable Formatting
1. **Inconsistent naming conventions**: With the exception of "minute_sleep", all dataframes adhere to the UpperCamelCase format. However, "minute_sleep" uses both UpperCamelCase and lowercase formats. → All variable names will be standardised to follow the snake_case naming convention using the `clean_names()` function. This will make all the variable names consistent and easier to read.
2. **Different names for variables with the same meaning**: Although most columns with variables of the same meaning share consistent titles across all dataframes (e.g., "Id"), the date columns exhibit variations such as "ActivityDate," "ActivityDay," and "Time." → These variables will be renamed to follow the same title "activity_date." This will be helpful later during merging.
3. **Date Column's Data Type**: Currently, the date column is stored as a character type, which poses challenges for analysis. To address this, new columns will be created where the date will be converted into either date or date-time format using the `mdy()` and `mdy_hms()` functions. This standardized date-time formatting will ensure consistency across all datasets.

***Daily DataFrames***
```r
# Naming conventions and date variable formatting of Daily DataFrames
clean_daily_activity <- daily_activity %>% 
  clean_names() 
clean_daily_activity$activity_date_ymd <- mdy(clean_daily_activity$activity_date) 
print("-----Clean Daily Activity-----")
glimpse(clean_daily_activity)

clean_daily_calories <- daily_calories %>% 
  rename(activity_date = ActivityDay) %>% 
  clean_names()
clean_daily_calories$activity_date_ymd <- mdy(clean_daily_calories$activity_date) 
print("-----Clean Daily Calories-----")
glimpse(clean_daily_calories)

clean_daily_intensities <- daily_intensities %>% 
  rename(activity_date = ActivityDay) %>% 
  clean_names()
clean_daily_intensities$activity_date_ymd <- mdy(clean_daily_intensities$activity_date)
print("-----Clean Daily Intensities-----")
glimpse(clean_daily_intensities)

clean_daily_steps <- daily_steps %>% 
  rename(activity_date = ActivityDay,
         total_steps = StepTotal) %>% 
  clean_names()
clean_daily_steps$activity_date_ymd <- mdy(clean_daily_steps$activity_date)
print("-----Clean Daily Steps-----")
glimpse(clean_daily_steps)

clean_daily_sleep <- daily_sleep %>% 
  rename(activity_date = SleepDay) %>% 
  clean_names() 
clean_daily_sleep$activity_date_ymd <- mdy_hms(clean_daily_sleep$activity_date, tz=Sys.timezone())
print("-----Clean Daily Sleep-----")
glimpse(clean_daily_sleep)

clean_weight_log_info <- weight_log_info %>% 
  rename(activity_date = Date,
         weight_kg = WeightKg,
         weight_lb = WeightPounds,
         manual_report = IsManualReport) %>% 
  clean_names()
clean_weight_log_info$activity_date_ymdhms <- mdy_hms(clean_weight_log_info$activity_date, tz=Sys.timezone())
print("-----Clean Weight Log Info-----")
glimpse(clean_weight_log_info)
```

```{r, results='markup'}
[1] "-----Clean Daily Activity-----"
Rows: 940
Columns: 16
$ id                         <dbl> 1503960366, 1503960366, 1503960366, 1503960…
$ activity_date              <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/1…
$ total_steps                <dbl> 13162, 10735, 10460, 9762, 12669, 9705, 130…
$ total_distance             <dbl> 8.50, 6.97, 6.74, 6.28, 8.16, 6.48, 8.59, 9…
$ tracker_distance           <dbl> 8.50, 6.97, 6.74, 6.28, 8.16, 6.48, 8.59, 9…
$ logged_activities_distance <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
$ very_active_distance       <dbl> 1.88, 1.57, 2.44, 2.14, 2.71, 3.19, 3.25, 3…
$ moderately_active_distance <dbl> 0.55, 0.69, 0.40, 1.26, 0.41, 0.78, 0.64, 1…
$ light_active_distance      <dbl> 6.06, 4.71, 3.91, 2.83, 5.04, 2.51, 4.71, 5…
$ sedentary_active_distance  <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
$ very_active_minutes        <dbl> 25, 21, 30, 29, 36, 38, 42, 50, 28, 19, 66,…
$ fairly_active_minutes      <dbl> 13, 19, 11, 34, 10, 20, 16, 31, 12, 8, 27, …
$ lightly_active_minutes     <dbl> 328, 217, 181, 209, 221, 164, 233, 264, 205…
$ sedentary_minutes          <dbl> 728, 776, 1218, 726, 773, 539, 1149, 775, 8…
$ calories                   <dbl> 1985, 1797, 1776, 1745, 1863, 1728, 1921, 2…
$ activity_date_ymd          <date> 2016-04-12, 2016-04-13, 2016-04-14, 2016-0…
[1] "-----Clean Daily Calories-----"
Rows: 940
Columns: 4
$ id                <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503…
$ activity_date     <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/2016", …
$ calories          <dbl> 1985, 1797, 1776, 1745, 1863, 1728, 1921, 2035, 1786…
$ activity_date_ymd <date> 2016-04-12, 2016-04-13, 2016-04-14, 2016-04-15, 201…
[1] "-----Clean Daily Intensities-----"
Rows: 940
Columns: 11
$ id                         <dbl> 1503960366, 1503960366, 1503960366, 1503960…
$ activity_date              <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/1…
$ sedentary_minutes          <dbl> 728, 776, 1218, 726, 773, 539, 1149, 775, 8…
$ lightly_active_minutes     <dbl> 328, 217, 181, 209, 221, 164, 233, 264, 205…
$ fairly_active_minutes      <dbl> 13, 19, 11, 34, 10, 20, 16, 31, 12, 8, 27, …
$ very_active_minutes        <dbl> 25, 21, 30, 29, 36, 38, 42, 50, 28, 19, 66,…
$ sedentary_active_distance  <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
$ light_active_distance      <dbl> 6.06, 4.71, 3.91, 2.83, 5.04, 2.51, 4.71, 5…
$ moderately_active_distance <dbl> 0.55, 0.69, 0.40, 1.26, 0.41, 0.78, 0.64, 1…
$ very_active_distance       <dbl> 1.88, 1.57, 2.44, 2.14, 2.71, 3.19, 3.25, 3…
$ activity_date_ymd          <date> 2016-04-12, 2016-04-13, 2016-04-14, 2016-0…
[1] "-----Clean Daily Steps-----"
Rows: 940
Columns: 4
$ id                <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1503…
$ activity_date     <chr> "4/12/2016", "4/13/2016", "4/14/2016", "4/15/2016", …
$ total_steps       <dbl> 13162, 10735, 10460, 9762, 12669, 9705, 13019, 15506…
$ activity_date_ymd <date> 2016-04-12, 2016-04-13, 2016-04-14, 2016-04-15, 201…
[1] "-----Clean Daily Sleep-----"
Rows: 413
Columns: 6
$ id                   <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1…
$ activity_date        <chr> "4/12/2016 12:00:00 AM", "4/13/2016 12:00:00 AM",…
$ total_sleep_records  <dbl> 1, 2, 1, 2, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1…
$ total_minutes_asleep <dbl> 327, 384, 412, 340, 700, 304, 360, 325, 361, 430,…
$ total_time_in_bed    <dbl> 346, 407, 442, 367, 712, 320, 377, 364, 384, 449,…
$ activity_date_ymd    <dttm> 2016-04-12, 2016-04-13, 2016-04-15, 2016-04-16, …
[1] "-----Clean Weight Log Info-----"
Rows: 67
Columns: 9
$ id                   <dbl> 1503960366, 1503960366, 1927972279, 2873212765, 2…
$ activity_date        <chr> "5/2/2016 11:59:59 PM", "5/3/2016 11:59:59 PM", "…
$ weight_kg            <dbl> 52.6, 52.6, 133.5, 56.7, 57.3, 72.4, 72.3, 69.7, …
$ weight_lb            <dbl> 115.9631, 115.9631, 294.3171, 125.0021, 126.3249,…
$ fat                  <dbl> 22, NA, NA, NA, NA, 25, NA, NA, NA, NA, NA, NA, N…
$ bmi                  <dbl> 22.65, 22.65, 47.54, 21.45, 21.69, 27.45, 27.38, …
$ manual_report        <lgl> TRUE, TRUE, FALSE, TRUE, TRUE, TRUE, TRUE, TRUE, …
$ log_id               <dbl> 1.462234e+12, 1.462320e+12, 1.460510e+12, 1.46128…
$ activity_date_ymdhms <dttm> 2016-05-02 23:59:59, 2016-05-03 23:59:59, 2016-0…
```
***Hourly DataFrames***
```r
# Naming conventions and date variable formatting of Hourly DataFrames
clean_hourly_calories <- hourly_calories %>% 
  clean_names()
clean_hourly_calories$activity_hour_ymdhms <- mdy_hms(clean_hourly_calories$activity_hour, tz=Sys.timezone())
print("-----Clean Hourly Calories-----")
glimpse(clean_hourly_calories)

clean_hourly_intensities <- hourly_intensities %>% 
  clean_names()
clean_hourly_intensities$activity_hour_ymdhms <- mdy_hms(clean_hourly_intensities$activity_hour, tz=Sys.timezone())
print("-----Clean Hourly Intensities-----")
glimpse(clean_hourly_intensities)

clean_hourly_steps <- hourly_steps %>% 
  rename(total_steps = StepTotal) %>% 
  clean_names()
clean_hourly_steps$activity_hour_ymdhms <- mdy_hms(clean_hourly_steps$activity_hour, tz=Sys.timezone())
print("-----Clean Hourly Steps-----")
glimpse(clean_hourly_steps)
```
```{r, results='markup'}
[1] "-----Clean Hourly Calories-----"
Rows: 22,099
Columns: 4
$ id                   <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1…
$ activity_hour        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", …
$ calories             <dbl> 81, 61, 59, 47, 48, 48, 48, 47, 68, 141, 99, 76, …
$ activity_hour_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 01:00:00, 2016-0…
[1] "-----Clean Hourly Intensities-----"
Rows: 22,099
Columns: 5
$ id                   <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1…
$ activity_hour        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", …
$ total_intensity      <dbl> 20, 8, 7, 0, 0, 0, 0, 0, 13, 30, 29, 12, 11, 6, 3…
$ average_intensity    <dbl> 0.333333, 0.133333, 0.116667, 0.000000, 0.000000,…
$ activity_hour_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 01:00:00, 2016-0…
[1] "-----Clean Hourly Steps-----"
Rows: 22,099
Columns: 4
$ id                   <dbl> 1503960366, 1503960366, 1503960366, 1503960366, 1…
$ activity_hour        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 1:00:00 AM", …
$ total_steps          <dbl> 373, 160, 151, 0, 0, 0, 0, 0, 250, 1864, 676, 360…
$ activity_hour_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 01:00:00, 2016-0…
```
***Minute DataFrames***
```r
# Naming conventions and date variabe formatting of Minute DataFrames
clean_minute_calories <- minute_calories_narrow %>% 
  clean_names()
clean_minute_calories$activity_minute_ymdhms <- mdy_hms(clean_minute_calories$activity_minute, tz=Sys.timezone())
print("-----Clean Minute Calories-----")
glimpse(clean_minute_calories)

clean_minute_intensities <- minute_intensities_narrow %>% 
  clean_names()
clean_minute_intensities$activity_minute_ymdhms <- mdy_hms(clean_minute_intensities$activity_minute, tz=Sys.timezone())
print("-----Clean Minute Intensities-----")
glimpse(clean_minute_intensities)

clean_minute_METs <- minute_METs_narrow %>% 
  rename(mets = METs) %>% 
  clean_names()
clean_minute_METs$activity_minute_ymdhms <- mdy_hms(clean_minute_METs$activity_minute, tz=Sys.timezone())
print("-----Clean Minute METs-----")
glimpse(clean_minute_METs)

clean_minute_sleep <- minute_sleep %>% 
  rename(activity_minute = date,
         sleep_state = value) %>% 
  clean_names()
clean_minute_sleep$activity_minute_ymdhms <- mdy_hms(clean_minute_sleep$activity_minute, tz=Sys.timezone())
print("-----Clean Minute Sleep-----")
glimpse(clean_minute_sleep)

clean_minute_steps <- minute_steps_narrow %>% 
  rename(total_steps = Steps) %>% 
  clean_names()
clean_minute_steps$activity_minute_ymdhms <- mdy_hms(clean_minute_steps$activity_minute, tz=Sys.timezone())
print("-----Clean Minute Steps-----")
glimpse(clean_minute_steps)
```
```{r, results='markup'}
[1] "-----Clean Minute Calories-----"
Rows: 1,325,580
Columns: 4
$ id                     <dbl> 1503960366, 1503960366, 1503960366, 1503960366,…
$ activity_minute        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM…
$ calories               <dbl> 0.7865, 0.7865, 0.7865, 0.7865, 0.7865, 0.9438,…
$ activity_minute_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 00:01:00, 2016…
[1] "-----Clean Minute Intensities-----"
Rows: 1,325,580
Columns: 4
$ id                     <dbl> 1503960366, 1503960366, 1503960366, 1503960366,…
$ activity_minute        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM…
$ intensity              <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…
$ activity_minute_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 00:01:00, 2016…
[1] "-----Clean Minute METs-----"
Rows: 1,325,580
Columns: 4
$ id                     <dbl> 1503960366, 1503960366, 1503960366, 1503960366,…
$ activity_minute        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM…
$ mets                   <dbl> 10, 10, 10, 10, 10, 12, 12, 12, 12, 12, 12, 12,…
$ activity_minute_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 00:01:00, 2016…
[1] "-----Clean Minute Sleep-----"
Rows: 188,521
Columns: 5
$ id                     <dbl> 1503960366, 1503960366, 1503960366, 1503960366,…
$ activity_minute        <chr> "4/12/2016 2:47:30 AM", "4/12/2016 2:48:30 AM",…
$ sleep_state            <dbl> 3, 2, 1, 1, 1, 1, 1, 2, 2, 2, 3, 3, 3, 3, 3, 2,…
$ log_id                 <dbl> 11380564589, 11380564589, 11380564589, 11380564…
$ activity_minute_ymdhms <dttm> 2016-04-12 02:47:30, 2016-04-12 02:48:30, 2016…
[1] "-----Clean Minute Steps-----"
Rows: 1,325,580
Columns: 4
$ id                     <dbl> 1503960366, 1503960366, 1503960366, 1503960366,…
$ activity_minute        <chr> "4/12/2016 12:00:00 AM", "4/12/2016 12:01:00 AM…
$ total_steps            <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…
$ activity_minute_ymdhms <dttm> 2016-04-12 00:00:00, 2016-04-12 00:01:00, 2016…
```
***Second DataFrame***
```r
# Naming conventions and date variable formatting of Second DataFrame
clean_heartrate_seconds <- heartrate_seconds %>% 
  rename(activity_second = Time,
         heartrate = Value) %>% 
  clean_names()
clean_heartrate_seconds$activity_second_ymdhms <- mdy_hms(clean_heartrate_seconds$activity_second, tz=Sys.timezone())
print("-----Clean Heartrate Seconds-----")
glimpse(clean_heartrate_seconds)
```
```{r, results='markup'}
[1] "-----Clean Heartrate Seconds-----"
Rows: 2,483,658
Columns: 4
$ id                     <dbl> 2022484408, 2022484408, 2022484408, 2022484408,…
$ activity_second        <chr> "4/12/2016 7:21:00 AM", "4/12/2016 7:21:05 AM",…
$ heartrate              <dbl> 97, 102, 105, 103, 101, 95, 91, 93, 94, 93, 92,…
$ activity_second_ymdhms <dttm> 2016-04-12 07:21:00, 2016-04-12 07:21:05, 2016…
```
### 3.4.2 Unique Participant IDs
According to the data description, each dataset should contain 30 unique participant IDs. To verify this, the number of unique participants will be assessed using the `n_unique()` function. 

***Daily DataFrames***
```r
# Unique participant IDs: Daily DataFrames
print("Daily Activity")
n_unique(clean_daily_activity$id)

print("Daily Calories")
n_unique(clean_daily_calories$id)

print("Daily Intensities")
n_unique(clean_daily_intensities$id)

print("Daily Steps")
n_unique(clean_daily_steps$id)

print("Daily Sleep")
n_unique(clean_daily_sleep$id)

print("Daily Weight Log Info")
n_unique(clean_weight_log_info$id)
```
```{r, results='markup'}
[1] "Daily Activity"
33
[1] "Daily Calories"
33
[1] "Daily Intensities"
33
[1] "Daily Steps"
33
[1] "Daily Sleep"
24
[1] "Daily Weight Log Info"
8
```
***Hourly DataFrames***
```r
# Unique participant IDs: Hourly DataFrames
print("Hourly Calories")
n_unique(clean_hourly_calories$id)

print("Hourly Intensities")
n_unique(clean_hourly_intensities$id)

print("Hourly Steps")
n_unique(clean_hourly_steps$id)
```
```{r, results='markup'}
[1] "Hourly Calories"
33
[1] "Hourly Intensities"
33
[1] "Hourly Steps"
33
```
***Minute DataFrames***
```r
# Unique participant IDs: Minute DataFrames
print("Minute Calories")
n_unique(clean_minute_calories$id)

print("Minute Intensities")
n_unique(clean_minute_intensities$id)

print("Minute METs")
n_unique(clean_minute_METs$id)

print("Minute Sleep")
n_unique(clean_minute_sleep$id)

print("Minute Steps")
n_unique(clean_minute_steps$id)
```
```{r, results='markup'}
[1] "Minute Calories"
33
[1] "Minute Intensities"
33
[1] "Minute METs"
33
[1] "Minute Sleep"
24
[1] "Minute Steps"
33
```
***Second DataFrames***
```r
# Unique participant IDs: Second DataFrame
print("Second Heartrate")
n_unique(clean_heartrate_seconds$id)
```
```{r, results='markup'}
[1] "Second Heartrate"
14
```
#### Observation
* Based on the results, the datasets appear to be inconsistent with the author's description, showing predominantly 33 distinct IDs, three more than expected.
* Most datasets have 33 participants, except for sleep (24), weight (8), and heart rate (14). This discrepancy implies that sleep, weight, and heart rate datasets are incomplete. This inconsistency might be because tracked activities are being automatically recognised and recorded by the device through movement. Unlike activities, weight measurements require manual entry into Fitbit, while heart rate tracking may necessitate user activation. Consequently, participants may not have consistently recorded their weight or activated heart rate tracking, leading to incomplete datasets.

#### Actions Taken
* Given the limited participant counts in the weight (8) and heart datasets (14), these datasets will be excluded from further analysis as the sample size is not significant enough to make any conclusions.
<br>
<br>

### 3.4.3 Number of Active Days
Each dataset is expected to span 31 days. To confirm this, the number of active days in each dataset will be assessed using the `n_unique()` function. 

***Daily DataFrames***
```r
# Unique number of active days: Daily DataFrames
print("Daily Activity")
n_unique(clean_daily_activity$activity_date_ymd)

print("Daily Calories")
n_unique(clean_daily_calories$activity_date_ymd)

print("Daily Intensities")
n_unique(clean_daily_intensities$activity_date_ymd)

print("Daily Steps")
n_unique(clean_daily_steps$activity_date_ymd)

print("Daily Sleep")
n_unique(clean_daily_sleep$activity_date_ymd)
```
```{r, results='markup'}
[1] "Daily Activity"
31
[1] "Daily Calories"
31
[1] "Daily Intensities"
31
[1] "Daily Steps"
31
[1] "Daily Sleep"
31
```
***Hourly DataFrames***
```r
# Unique number of active days: Hourly DataFrames
print("Hourly Calories")
n_unique(date(clean_hourly_calories$activity_hour_ymdhms))

print("Hourly Intensities")
n_unique(date(clean_hourly_intensities$activity_hour_ymdhms))

print("Hourly Steps")
n_unique(date(clean_hourly_steps$activity_hour_ymdhms))
```
```{r, results='markup'}
[1] "Hourly Calories"
31
[1] "Hourly Intensities"
31
[1] "Hourly Steps"
31
```
***Minute DataFrames***
```r
# Unique number of active days: Minute DataFrames
print("Minute Calories")
n_unique(date(clean_minute_calories$activity_minute_ymdhms))

print("Minute Intensities")
n_unique(date(clean_minute_intensities$activity_minute_ymdhms))

print("Minute METs")
n_unique(date(clean_minute_METs$activity_minute_ymdhms))

print("Minute Sleep")
n_unique(date(clean_minute_sleep$activity_minute_ymdhms))

print("Minute Steps")
n_unique(date(clean_minute_steps$activity_minute_ymdhms))
```
```{r, results='markup'}
[1] "Minute Calories"
31
[1] "Minute Intensities"
31
[1] "Minute METs"
31
[1] "Minute Sleep"
32
[1] "Minute Steps"
31
```
#### Observation
Most datasets exhibit 31 active days, aligning with the expected duration of the research period. However, the "minute_sleep" dataset displays 32 active days. The research was supposed to start on 04/12/2016 and end 05/12/2016 (= 31 days). However, some participants went to bed before 12am on 04/11/2016; therefore, that date was also included in the data, amounting to 32 days.
<br>
<br>

### 3.4.4 Participants' Logged Activity
To ensure participant engagement throughout the entire 31-day research period, the number of logged activities will be examined.
# Checking participant's logged activity
```r
clean_daily_activity %>% 
  group_by(id) %>% 
  count() %>% 
  arrange(n) %>% 
  tibble() %>% 
  print(n=33)
```
```{r, results='markup'}
# A tibble: 33 × 2
           id     n
        <dbl> <int>
 1 4057192912     4
 2 2347167796    18
 3 8253242879    19
 4 3372868164    20
 5 6775888955    26
 6 7007744171    26
 7 6117666160    28
 8 6290855005    29
 9 8792009665    29
10 1644430081    30
11 3977333714    30
12 5577150313    30
13 1503960366    31
14 1624580081    31
15 1844505072    31
16 1927972279    31
17 2022484408    31
18 2026352035    31
19 2320127002    31
20 2873212765    31
21 4020332650    31
22 4319703577    31
23 4388161847    31
24 4445114986    31
25 4558609924    31
26 4702921684    31
27 5553957443    31
28 6962181067    31
29 7086361926    31
30 8053475328    31
31 8378563200    31
32 8583815059    31
33 8877689391    31
```
#### Observation
Participant with ID# 4057192912 has only 4 logged activities, which is significantly low. Although considering removal, given the already limited participant pool, the participant's data will be kept.
<br>
<br>

### 3.4.5 Missing Values
The number of missing values in each dataset will be examined using the `sum(is.na(x))` and `which(is.na(x))` functions. 

***Daily DataFrames***
```r
# Checking for missing values: Daily DataFrames
print ("-----Daily Activity-----")
if (sum(is.na(clean_daily_activity)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_daily_activity))
} else {
  print("No missing values")
}

print("-----Daily Calories-----")
if (sum(is.na(clean_daily_calories)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_daily_calories))
} else {
  print("No missing values")
}

print("-----Daily Intensities-----")
if (sum(is.na(clean_daily_intensities)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_daily_intensities))
} else {
  print("No missing values")
}

print("-----Daily Steps-----")
if (sum(is.na(clean_daily_steps)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_daily_steps))
} else {
  print("No missing values")
}

print("-----Daily Sleep-----")
if (sum(is.na(clean_daily_sleep)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_daily_sleep))
} else {
  print("No missing values")
}
```
```{r, results='markup'}
[1] "-----Daily Activity-----"
[1] "No missing values"
[1] "-----Daily Calories-----"
[1] "No missing values"
[1] "-----Daily Intensities-----"
[1] "No missing values"
[1] "-----Daily Steps-----"
[1] "No missing values"
[1] "-----Daily Sleep-----"
[1] "No missing values"
```
***Hourly DataFrames***
```r
# Checking for missing values: Hourly DataFrames
print("-----Hourly Calories-----")
if (sum(is.na(clean_hourly_calories)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_hourly_calories))
} else {
  print("No missing values")
}

print("-----Hourly Intensities-----")
if (sum(is.na(clean_hourly_intensities)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_hourly_intensities))
} else {
  print("No missing values")
}

print("-----Hourly Steps-----")
if (sum(is.na(clean_hourly_steps)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_hourly_steps))
} else {
  print("No missing values")
}
```
```{r, results='markup'}
[1] "-----Hourly Calories-----"
[1] "No missing values"
[1] "-----Hourly Intensities-----"
[1] "No missing values"
[1] "-----Hourly Steps-----"
[1] "No missing values"
```
***Minute DataFrames***
```r
# Checking for missing values: Minute DataFrames
print("-----Minute Calories-----")
if (sum(is.na(clean_minute_calories)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_minute_calories))
} else {
  print("No missing values")
}

print("-----Minute Intensities-----")
if (sum(is.na(clean_minute_intensities)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_minute_intensities))
} else {
  print("No missing values")
}

print("-----Minute METs-----")
if (sum(is.na(clean_minute_METs)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_minute_METs))
} else {
  print("No missing values")
}

print("-----Minute Sleep-----")
if (sum(is.na(clean_minute_sleep)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_minute_sleep))
} else {
  print("No missing values")
}

print("-----Minute Steps-----")
if (sum(is.na(clean_minute_steps)) !=0) {
  print("Position of missing values - ")
  which(is.na(clean_minute_steps))
} else {
  print("No missing values")
}
```
```{r, results='markup'}
[1] "-----Minute Calories-----"
[1] "No missing values"
[1] "-----Minute Intensities-----"
[1] "No missing values"
[1] "-----Minute METs-----"
[1] "No missing values"
[1] "-----Minute Sleep-----"
[1] "No missing values"
[1] "-----Minute Steps-----"
[1] "No missing values"
```
#### Observation
There are no missing values. 
<br>
<br>

### 3.4.6 Removing Duplicates
Duplicate data can cause inaccurate reporting. To find out if there are any duplicates, the `sum(duplicated())` function will be used. 

***Daily DataFrames***
```r
# Checking for duplicates: Daily DataFrames
print("Daily Activity")
sum(duplicated(clean_daily_activity))

print("Daily Calories")
sum(duplicated(clean_daily_calories))

print("Daily Intensities")
sum(duplicated(clean_daily_intensities))

print("Daily Steps")
sum(duplicated(clean_daily_steps))

print("Daily Sleep")
sum(duplicated(clean_daily_sleep))
```
```{r, results='markup'}
[1] "Daily Activity"
0
[1] "Daily Calories"
0
[1] "Daily Intensities"
0
[1] "Daily Steps"
0
[1] "Daily Sleep"
3
```
