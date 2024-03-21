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

```{r}
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

```{r}
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
```{r, results='markup'}
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
