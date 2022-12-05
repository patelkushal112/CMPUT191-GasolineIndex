# The Gasoline Index - Kushal Patel 

## Why Gasoline?

In an era where transportation is a necessity, gasoline serves to be an important unavoidable cost of transportation. The motivation behind the selection of gasoline stems from my experiences over the past couple of years. As a university student, money is scarce and valuable. Therefore, I attempted to prevent my downfall into debt via means of a budget. Through the first couple of months of budgetting I came to the realization as to what most of my money is going towards, and you can probably guess what it is based on the title of this website. That's right! Gasoline!! For that reason I wanted to base my project on the price of gas worldwide, to possibly see if I should be living in a different part of the world, and not Canada. 

## The Index 

### 1. Scrape all the necessary data from the sources

All the necessary data was scraped into different tables from each source:
- Data on worldwide gas prices -> gas_prices: https://www.numbeo.com/cost-of-living/prices_by_country.jsp?itemId=24&displayCurrency=CAD
- Data on currency codes -> currency_codes: https://www.iban.com/currency-codes
- Data on GST -> taxes_table: taxes.csv
- Data on exchange rates -> exchange_rates: https://www.tpsgc-pwgsc.gc.ca/cgi-bin/recgen/er.pl?Language=E
- Data on currency symbols -> symbols: https://www.eurochange.co.uk/travel/tips/world-currency-abbreviations-symbols-and-codes-travel-money

### 2. Tidying Each Table & Adding it to main gas_prices Table

#### gas_prices Table
The initial gas_prices table had to to be tidied up by removing the "rank" column
