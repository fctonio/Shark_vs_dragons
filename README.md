# hello

<img src="https://bit.ly/2VnXWr2" alt="Ironhack Logo" width="100"/>

# Sharks vs Dragons
*Group project, week 3
*Julia, Anton, Imogen*

*August 2020 cohort, Berlin, 28.08.20*

## Content
- [Project Description](#project-description)
- [Questions & Hypotheses](#questions-hypotheses)
- [Dataset](#dataset)
- [Database](#database)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

## Project Description
Write a short introduction to your project: 3-5 sentences about the context of your topic and why you chose it.

We decided to examine data from the reality TV show franchises 'Dragon's Den' (UK) and 'Shark Tank' (USA). In the show, entrepreneurs pitch business ideas or businesses to a panel of investors (referred to as 'Dragons' or 'Sharks', respectively), and the investors then decide whether to invest in the company. We were interested in comparing the two franchises to look for points of commonality and difference. 


## Questions & Hypotheses
What are the questions you would like to answer with your analysis? What did you feel were the answers to those questions before answering them with data?

The aim of the project at hand is to merge different datasets and to prepare them for a deeper data analysis on the differences and similarities between Shark Tank US and Dragon's Den UK.

The following questions are to be addressed:
1. What number of episodes exist in total and per season?
2. What are the top ten overall products with the highest valuation and how can they be categorized?
3. What is the av. valuation per company?

## Dataset
What dataset (or datasets) did you use? What are the different sources you used (e.g. APIs, web scrapping, etc.)? Provide links to the data if available and describe the data briefly.

We were able to locate two suitable datasets in csv form for the American franchise, Shark Tank. However, we could not locate a suitable dataset for Dragon's Den, and therefore had to use web scraping to access comparable information. 

The project dataset was obtained through directly downloading raw data as well as webscraping:

**dataset_1: shark_tank.csv as "shark_ent" (shark entrepreneurs)**
- download of raw data
Link: https://docs.google.com/spreadsheets/d/1Lr0gi_QJB_JU0lBMjJ7WiBRxA0loml1FlM-KlmKsaEY/edit#gid=0
Source: "Shark Tank Data Analysis 10 Seasons", www.thehustle.co
https://thehustle.co/shark-tank-data-analysis-10-seasons/?utm_source=sunday&utm_medium=email&utm_campaign=05%2F19%20-%20shark%20tank&utm_content=https%3A%2F%2Fthehustle.co%2Fshark-tank-data-analysis-10-seasons%2F
Last edited: 19 May 2019
Last accessed: 27 Aug 2020

**dataset_2: shark_deals.csv as "shark_inv" (shark investors)**
- download of raw data
Link: https://www.kaggle.com/neiljs/all-shark-tank-us-pitches-deals
Source: www.kaggle.com
Last edited: 2017
Last accessed: 27 Aug 2020

**dataset_3: dragons_den.csv**
- webscraping
Link:https://en.wikipedia.org/wiki/Dragons'_Den_(British_TV_programme)#Statistics 
Source: www.wikipedia.org
Last edited: 23 Aug 2020
Last accessed: 27 Aug 2020


## Database
What is the structure of your database? Have you created more than one table and if yes, how are they related to each other?

Dataset_1 and dataset_2 focus on Shark Tank US, while dataset_3 focuses on Dragon's Den UK.

While dataset_1 focuses more on shark entrepreneurs, dataset_2 has additional information on shark investors.
The datasets are merged on shark investors on the product name, taking dataset_2 as a base.

Dataset_3 was obtained for comparison through webscrapping data present in similar form in the merge of dataset_1 and dataset_2.


## Workflow
Outline the workflow you used in your project. What are the steps you went through?

First we decided on our topic and began a broad search for data. We compared various data sources found, before deciding to use two csv files on Shark Tank. Julia and Imogen merged those two datasets and cleaned them, while Anton webscraped the Wikipedia page on Dragon's Den. We then examined our datasets and began to conduct small analyses on them. 

**Cleaning the merged Shark Tank dataset involved the following methods:**
- Improved column names:
    - Removed whitespaces from column names
    - Set column names to lowercase
    - Replaced spaces in column names with underscores
    - Renamed columns of one dataset to better match the other
- Changed values in columns:
    - Extracted the state and saved it to 'location' column
    - Replaced initials in 'deal_shark' column with full names of investors
- Reduced missing values:
    - Removed rows from seasons 7 & 8 as one dataset only went up to season 6
    - Dropped rows with too many missing values
    - Replace null values in 'deal_shark' column with 'Unknown'
- Removed duplicate columns
    - Compared 'pitched_business_desc' and 'description', dropped 'description'
    - Compared 'deal_status' and 'deal' columns & dropped 'deal'
    - Compared 'pitched_business_identifier' and 'title', dropped 'title'
    - Removed further duplicate columns
    - Removed unneccessary column 'multiple_entrepreneurs'
- Fixed incorrect data types
    - Changed data type from float to integer for 5 columns
- Reset index


## Organization
How did you organize your work? Did you use any tools like a kanban board?
What does your repository look like? Explain your folder and file structure.


We created a kanban board on Trello to organise and coordinate work among ourselves. That way, we could distinguish between tasks that needed to be done and tasks that would be nice to have if time permits. The kanban board also allowed us to assign tasks to one or more of us, making it easier to keep track of who was doing what. 


Our repository contains the following files:
- this README file
- csv files:
    - dataset_1: shark_tank.csv as "shark_ent" (shark entrepreneurs)
    - dataset_2: shark_deals.csv as "shark_inv" (shark investors)
    - dataset_3: dragons_den.csv
    - merged shark tank dataset (just started cleaning): shark_merged_copy.csv
    - cleaned shark tank dataset: shark_merged_clean.csv
    - webscraped Dragon's Den dataset: Dragons_den_web_scrape_wikipedia.csv
- jupyter notebook files:
    - jupyter file of merging 2 shark tank datasets: 1_shark_merged.ipynb
    - jupyter file of cleaning the merged shark tank dataset: 2.shark_merged_cleaning.ipynb
    - jupyter file of webscraping Dragon's Den dataset: Wikipedia-web-scraping.ipynb

**let's rename the files before submitting** 


## Links
Include links to your repository, slides and kanban board. Feel free to include any other links associated with your project.

[Repository](https://github.com/fctonio/Shark_vs_dragons) 
[Trello](https://trello.com/b/HXCiA8Xj/sharks-vs-dragons)
