# ds_salary_proj
An effective tool for estimating data scientist salaries

## Content

- [Collect the data](#collect-the-data)
- [Clean the data](#clean-the-data)

## Collect the data


The data for fetching information from [Glassdoor](https://www.glassdoor.com/Job/index.htm) was obtained through the Glassdoor website itself, which can be accessed at Glassdoor. To interact with the website and retrieve the data, the Selenium framework was used.

If you're interested in learning how to fetch data from Glassdoor using Selenium, I recommend checking out the following article: [Selenium Tutorial: Scraping Glassdoor.com in 10 Minutes](https://mersakarya.medium.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905). 
This tutorial provides a practical guide on how to scrape data from Glassdoor using Selenium.

Additionally, you can find the corresponding code and implementation details in the GitHub repository available at [link](https://github.com/arapfaik/scraping-glassdoor-selenium). This repository contains the necessary code and resources to help you get started with scraping Glassdoor using Selenium.

## Clean the data

In this project, the main focus is on the 'Salary Estimate' column, which contains information about the expected salary for different job positions. The cleaning process involves the following steps:

1. Removing rows with unknown salary estimates: Any rows where the 'Salary Estimate' is listed as '-1' are eliminated from the dataset. These rows likely represent missing or invalid data and are not useful for the analysis.

2. Extracting pure salary information: After removing the rows with unknown salary estimates, the 'Salary Estimate' column is further processed to remove any additional information that may be present, such as "(Glassdoor est.)". This extra information is likely added by the website or platform from which the data was collected and is not relevant to the analysis. By removing this extra information, the focus is solely on the numerical salary values themselves.
3. the next step in the cleaning process is to remove the dollar sign ($) and the 'K' sign (representing thousands) from the numerical salary values. This is done to convert the salaries into a consistent numerical format. To remove the dollar sign, a simple string replacement can be performed on the 'Salary Estimate' column. For example, if the salary value is "$70,000 - $90,000", the dollar sign is removed to obtain "70,000 - 90,000".
4.  To account for different salary types such as per hour or employer-provided, two additional columns will be added to the main DataFrame. These columns will indicate whether the salary is defined on an hourly basis or if no specific salary information is provided. For instance, a new column named "Hourly Salary" can be created, where a value of 1 indicates that the salary is defined per hour, and a value of 0 indicates that it is not an hourly-based salary.
5. After doing the above steps, we will separate the min and mx salaries and also claculate the avg salaries.