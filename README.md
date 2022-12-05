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

#### Gas Prices Table
- The only tidying required for the initial gas_prices table was dropping the "Rank" column, and renaming the "Gasoline (1 liter)" column to "Price (CAD)"

#### Currency Codes Table 
1. In order to add the currency_codes table to the gas_prices table, the "Country" column had to be changed from all uppercase to only capitalized. 
2. Then the table was joined with the gas_prices table using the two "Country" columns.
3. Finally, the useless columns were dropped ("Currency", "Number"). 

#### Symbols Table 
- The only tidying required for the initial symbols table was joining the table with the gas_prices table using the "Code" and "Currency Code" columns, and then dropping the column "Country and Currency".

#### Taxes Table 
1. The taxes_table was joined to the gas_prices table using the "country" and "Country" columns.
2. To tidy the table, the columns "incomeTax" and "corpTax" were dropped.
3. The "salesTax" column was renamed to "GST".
4. Finally, the values in the "GST" column were converted from a whole number (percentage) to a decimal that could be used for calculations

#### Exchange Rates Table 
1. The exchange_rates table was added to the gas_prices table using the columns "Code" and "Currency\xa0Code" columns.
2. Furthermore, the "Currency Description" column was also dropped to tidy up the final table. 

### 3. Add Columns to the Table of the Necessary Data required to Generate Graphs. 

1. Price (Country Currency including Tax) Column. 
- This column was generated with the use of the "Price (CAD)", "GST", and "Rate" columns. 
- The values in this column are the Price (CAD) converted to each corresponding country's currency using the Rate, and finally factoring in each GST before finalizing the values.

2. Price (CAD including Tax) Column. 
- This column was generated with the use of the "Price (Country Currency including Tax)", and "Rate" columns. 
- The values in this column are the Price (Country Currency including Tax) column with the values converted back into CAD using the different rates. 

3. Difference Column. 
- This column was generated with the use of the "Price (CAD including Tax)" column. 
- The values in this column are the Price (CAD including Tax) of each country subtracting the Price (CAD including Tax) of Canada.

### 4. Plot The Differences

I chose to plot both the "positive" and "negative" differences differently for ease of comparison. The various bar charts were generated using the barh method on the gas_prices table, specifically the "Difference" column. 

