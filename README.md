# DATA 512 Homework 1: Professionalism & Reproducibility

## Wikipedia Articles Traffic Analysis (Jul 2015 - Sep 2024)

### Project Overview

The goal of this project is to construct, analyze, and publish a dataset of monthly article traffic from the English Wikipedia for a predefined list of rare disease articles. The timeframe for data collection is from **July 1, 2015, through September 30, 2024**. This data will be used to generate three distinct time series datasets that record desktop, mobile, and cumulative (desktop + mobile) pageviews for each article. The main objective is to ensure reproducibility in data collection and analysis while following best practices for open scientific research, allowing for transparency and validation.

### Analysis Details

The project includes the following analyses:

1. **Maximum Average and Minimum Average**:
   - A graph containing series for the articles with the highest and lowest average monthly page requests for desktop and mobile access.
  
2. **Top 10 Peak Page Views**:
   - A graph containing time series for the top 10 article pages by largest (peak) page views over the entire timeframe, categorized by access type.
  
3. **Fewest Months of Data**:
   - A graph displaying time series for the articles that have the fewest months of available data.

### License

#### Data License
The source data is obtained from the [Wikimedia Pageviews API](https://wikimedia.org/api/rest_v1/). The data is provided under the **Creative Commons Attribution-ShareAlike 3.0 Unported License (CC BY-SA 3.0)**.

**Summary of the Terms of Use**:
According to Wikimedia's terms, any data extracted from Wikipedia must attribute the source and be shared under the same or compatible license. For this project, any dataset created must acknowledge the Wikimedia Foundation and must not be used in a manner that violates the privacy of Wikipedia's contributors or users.

The full terms of use for Wikimedia Foundation's content can be found [here](https://foundation.wikimedia.org/wiki/Terms_of_use).

#### Code Attribution

Snippets of the code were taken from a code example developed by **Dr. David W. McDonald** for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the **Creative Commons CC-BY license**.

### API Documentation

- **Wikimedia REST API**: [Pageviews API Documentation](https://wikimedia.org/api/rest_v1/)
- **Python requests module**: [Python requests module](https://docs.python-requests.org/en/latest/)

### Data Files

#### Inputs:
- **rare-disease_cleaned.AUG.2024.csv**
  - This file contains the list of articles in the following format and is used to filter the articles while fetching data from APIs.
    - **disease**: string - Name of the rare disease
    - **pageid**: integer - Wikipedia page ID
    - **url**: string - Wikipedia page URL

#### Generated Files:
- **[rare-disease_monthly_mobile_201501-202409.json](generated_datafiles%2Frare-disease_monthly_desktop_201501-202409.json)**
  - This JSON file contains monthly pageviews data for all articles accessed through mobile devices, including web and mobile app.
  - **Fields**:
    - **project**: string - Wikimedia project domain and subdomain.
    - **article**: string - Wikipedia page title.
    - **granularity**: string - Time interval between datapoints such as weekly, monthly etc.
    - **timestamp**: string - Timestamp in YYYYMMDDHH format.
    - **agent**: string -  Type of agent.
    - **views**: integer - The number of pageviews.

- **rare-disease_monthly_desktop_201501-202409.json**
  - This JSON file contains monthly pageviews data for all articles accessed through desktop devices.
  - **Fields**:
    - **project**: string - Wikimedia project domain and subdomain.
    - **article**: string - Wikipedia page title.
    - **granularity**: string - Time interval between datapoints such as weekly, monthly etc.
    - **timestamp**: string - Timestamp in YYYYMMDDHH format.
    - **agent**: string -  Type of agent.
    - **views**: integer - The number of pageviews.

- **rare-disease_monthly_cumulative_201501-202409.json**
  - This JSON file contains monthly pageviews data for all articles accessed through mobile devices (web and app) and desktop devices.
  - **Fields**:
    - **project**: string - Wikimedia project domain and subdomain.
    - **article**: string - Wikipedia page title.
    - **granularity**: string - Time interval between datapoints such as weekly, monthly etc.
    - **timestamp**: string - Timestamp in YYYYMMDDHH format.
    - **agent**: string -  Type of agent.
    - **views**: integer - The number of pageviews.
---
