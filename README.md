# Indian General Elections'24(LokSabha Elections) Data Analysis through web scraping
(Kalvium assignment)

This project involves scraping the information of the recently concluded Lok Sabha election from the Election Commission of India's website and building a report of key insights derived from the data. The analysis includes various visualizations to illustrate the findings.

## Requirements
- Python 3.x
- Libraries:
  - pandas
  - requests
  - BeautifulSoup
  - matplotlib
  - seaborn

## Data Scraping

The data was scraped from the Election Commission of India's website using the `requests` and `BeautifulSoup` libraries. The scraping process involved extracting the following information:

1. **State-wise Voting Data**:
    - State Name
    - Parliament Constituency
    - Winning Candidate
    - Total Votes
    - Margin
    - Party Name

2. **Party-wise Performance**:
    - Party Name
    - Won
    - Leading
    - Total Seats

Here is a sample code snippet to scrape the data:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

url = 'https://results.eci.gov.in'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')

# Extract data (this is an example and might need adjustment based on the actual website structure)
state_data = []
for option in soup.find(id='ctl00_ContentPlaceHolder1_Result1_ddlState').find_all('option'):
    state_data.append(option.text)

# Continue scraping the required details and store them in pandas DataFrame
```
