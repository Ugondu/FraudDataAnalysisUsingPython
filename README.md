# Webscrapping using BeautifulSoup and Pandas for Data Analysis


![image](https://github.com/user-attachments/assets/2f354a39-2d41-494f-9c7c-cdcb292d5f13)


# Table of contents

- [Objective](#objective)
- [Stages](#stages)
- [Development](#development)
  - [Dependencies](#dependencies)
  - [Tools](#tools)
  - [Data Transformation](#data-transformation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Findings](#findings)
  - [Insights](#insights)
- [Conclusion](#conclusion)


# Objective

- Introduction

This is a simple python script designed to scrape fraud cases from wikipedia using BeautifulSoup Python Module. Thw aim is to scrape data available on the web page for further analysis.

* Country
* Reported Fraud Cases Per 100,000
* Year

This python script scrapes from the [https://en.wikipedia.org/wiki/Fraud#United_Kingdom] website then transforms the data into pandas DataFrame for exporting as a csv file to the local machine.


# Stages 

- Development
- Exploratory Data Analysis

# Development

## Dependencies

### Some of the modules used in the script include:

* Beautiful Soup
* Requests
* Pandas
* Numpy
* Seaborn
* Missingno
* Matplotlib


## Tools

| Tool | Purpose |
| --- | --- |
| BeautifulSoup(Python Module) | Scrapping the data from webpage|
| Python Libraries(Pandas, Numpy) | Cleaning, testing, and analyzing the data |
| Matplotlib, Seaborn | Visualizing the data |
| GitHub | Hosting the project documentation and version control |


## Data Transformation

The extracted data from the webpage is converted to Pandas Data frame

```python
/*
# 1. Create a pandas DataFrame for headers
# 2. Rename column to remove superscript from web page
# 3. Append data from webpage to the pandas DataFrame
# 4. Export as a .csv file 

-- 1.
pd.DataFrame(columns = fraud_table_titles )

-- 2. 
df.rename(columns={"Reported annual fraudsper 100,000[47]" : "Reported annual fraud per 100,000"})

-- 3.
column_data = table.find_all('tr')
for row in column_data[1:]:
    row_data = row.find_all('td')
    rows = [data.text.strip() for data in row_data]
    length = len(df)
    df.loc[length] = rows

-- 4.
df.to_csv('fraud.csv', index =False)

```

# Exploratory Data Analysis

The exported data set is analysed to uncover insights, trends, and patterns using visualization and statistical techniques.

## Findings

From the data extracted, focus was on the following;

1. The total number of fraud cases reported by each country per year
2. The top 10 countries by reported fraud cases
3. The least 10 countries by reported cases
4. The top 5 year by reported cases.


### 1. The total number of fraud cases reported by each country per year

| Rank | year                   |No of country    |
|------|------------------------|-----------------|
| 1    | 2021                   | 1               | 
| 2    | 2015                   | 1               |
| 3    | 2017                   | 1               |
| 4    | 2014                   | 1               |
| 5    | 2018                   | 4               |
| 6    | 2016                   | 6               |
| 7    | 2020                   | 12              |
| 8    | 2022                   | 70              |


### 2. The top 10 countries by reported fraud cases

| Rank | Country                |No of cases      |
|------|------------------------|-----------------|
| 1    | Luxemborg              | 1               | 
| 2    | Austria                | 1               |
| 3    | Belguim                | 1               |
| 4    | Spain                  | 1               |
| 5    | Germany                | 4               |
| 6    | Denmark                | 6               |
| 7    | Finland                | 12              |
| 8    | Monaco                 | 70              |
| 9    | England and Wales      | 12              |
| 10   | Sweden                 | 70              |


### 3. The least 10 countries by reported cases

| Rank | Country                |No of cases      |
|------|------------------------|-----------------|
| 1    | Vatican                | 0               | 
| 2    | Bolivia                | 0               |
| 3    | Belize                 | 0               |
| 4    | Senegal                | 0.3             |
| 5    | Guatemala              | 0.5             |
| 6    | Kenya                  | 0.9             |
| 7    | St Vincent             | 1               |
| 8    | Lebanon                | 3               |
| 9    | Algeria                | 3.2             |
| 10   | Syria                  | 3.5             |


### 3. The top 5 year by reported cases on average

| Rank | year                   |Avg. No of cases |
|------|------------------------|-----------------|
| 1    | 2021                   | 1600            | 
| 2    | 2016                   | 400             |
| 3    | 2022                   | 250             |
| 4    | 2020                   | 150             |
| 5    | 2014                   | 100             |


## Insights

From the data we extracted, year 2022 has the highest number of countries with Reported Fraud Cases per 100,000. Year 2021 has the highest average number of fraud cases from the data available. 

Countries like Bolivia, Belize, and The Vatican City has zero fraud cases on the report, while Sweden, England and Wales, and Monaco has the highest number of cases.

# Conclusion

In future projects, a more diverse dataset will be considered for expansive analysis. Data from dynamic webpages will be attempted using more sophisticated tools and software for improvement and learning purposes.
