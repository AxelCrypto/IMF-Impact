# Impact of IMF on Developping Countries 🌍

#### What is the impact of IMF loans towards borrowers' GDP and Poverty Statistics. 

## Database Creation 📋

### I. IMF Database creation
#### Objective: Download a CSV of data from developping countries with GDP and Poverty indicators as well as IMF loans figures.  

~ **Step 1**: From the WorldBank.org I downloaded the usefull data.
- I selected all countries from south Asia, Latine America and Africa. 
- I selected the entire time horizon available: 1970 to 2021.
- I had access to 1442 indicators. I exctacted a short list of indicators coming from only two categories: 
  - Economic Policy & Debt
  - Poverty  
    - This was still 411 lines of data per country. I reviewed every line and decided to keep a short list of 40 indicators per country.


~ **Step 2**: Database cleaning (columns names, nulls, typos and types of data)

![series](Images/series.png)


### II. Exterior Debt to GDP per country 
#### Objective: What is the international borrowing situation of IMF borrowers ?  
In addition to the evolution of GDP and poverties indicators for each country financed by the IMF, knowing its debt % towards external countries in comparation to its GDP would be an interesting additional indicator.

![debt](Images/debt.png)


~ **Step 1**: Collect the data from https://en.wikipedia.org/wiki/List_of_countries_by_external_debt  
Use of BeautifulSoup.   
~ **Step 2**: Clean the data and export it to a DataFrame  
~ **Step 3**: Link the Data to the IMF DataFrame through a primary key "id_Name".  

### III. Credit Rating
#### Objective: Credits are not free. Neither are the ones accorded by IMF or the World Bank. Interest rates are often influenced by the nation's credit rating. How tend to be rated IMF borrowers ?   
~ **Step 1**: Using Selenium I extracted the ratings from: https://tradingeconomics.com/country-list/rating  
~ **Step 2**: Clean the data and export it to a DataFrame    
~ **Step 3**: Link the Data to the IMF DataFrame through a primary key "id_Rating".  

![ratings](Images/ratings.png)



## Database Exportation to SQL 📚
I uploaded the three tables to SQL.  
IMF is linked to the table debt and the table ratings through the foreign keys 'id_Name' and 'id_Ratings'

![sql ](Images/sql.png)

complete view :
![complete view ](Images/complete view.png)


## Analysis 📊

78 countries from Latin America, South Asia or Africa received loans from the IMF.
I realised a random sample and obtain to analyse the 5 following countries:
![sample ](Images/sample.png)


From my still long short list of indicators I decided to select the following ones:

- IMF Loans indicators:   
  - 'Use of IMF credit (DOD, current US$)' : Total outstanding Loan from IMF  
  - 'Debt service on external debt' : sum of the principal repayments and interest payments actually made on these debts.
  - 'Adjusted net national income (annual % growth)' : total dollar value of everything produced by a country and the income its residents receive (Like GDP but only for resident)
  - 'Inflation, GDP deflator (annual %)' : inflation of local currency
 
- 'GDP growth (annual %)' : Increase of GDP


- Exports and Imports : 
  - 'Exports of goods and services (current US$)': Total Exports
  - External balance on goods and services (% of GDP) : X-M
  'Current account balance (% of GDP)' : X-M as % of GDP

- poverty:
  - 'Income share held by highest 20%'
  - Income share held by lowest 10%
  - Poverty headcount ratio at national poverty lines (% of population) - Bangladesh
  - Income share held by highest 10%
  - Income share held by lowest 20%



###  Uganda 
Increase of IMF loans towards $ 1.4 billion in 2021:   
![Uganda1](Results/Uganda 1.png)

Debt is never free. $800M of principal + interest in 2021 alone: 
![Uganda2](Results/Uganda2.png)

Inflation stable
![Uganda3](Results/Uganda3.png)

GDP increased until 1994. Shrinking since then.
![Uganda4](Results/Uganda4.png)

Exports skyrocked:
![Uganda5](Results/Uganda5.png)

But the current account balance is deeply negative showing that imports > exports:  
![Uganda7](Results/Uganda7.png)

% of Poverty seems improving:
![Uganda8](Results/Uganda8.png)

10% richer got a slightly richer with 35% of incomes:
![Uganda9](Results/Uganda9.png)

10% poorer remained stagnant with 2.5% of incomes:
![Uganda10](Results/Uganda 10.png)

Based on SQL query: 
- Uganda has a credit rating of B-, an external debt to GDP of 41% and an External Debt $37M bl



### Bangladesh 
Increase of IMF loans towards $ 3.2 billion in 2021:   
![bangladesh1](Results/bangladesh1.png)

Debt is never free. $5.7bl of principal + interest in 2021 alone: 
![bangladesh2](Results/bangladesh2.png)

The net income as % of gdp going to the population tanks close to 0:  
![bangladesh3](Results/bangladesh3.png)

GDP increase is stable at around 5%. So no sign of improvement since IMF loans.
![bangladesh5](Results/bangladesh5.png)

Exports skyrocked:
![bangladesh6](Results/bangladesh6.png)

But the current account balance is negative showing that imports > exports:  
![bangladesh7](Results/bangladesh7.png)

% of Poverty seems improving:
![bangladesh9](Results/bangladesh8.png)

10% richer got a richer with currently 25% of total incomes:
![bangladesh10](Results/bangladesh9.png)

10% poorer remained stagnant with aroung 3.5% of incomes:
![bangladesh10](Results/bangladesh10.png)

Based on SQL query: 
- banglades has a credit rating of BB-, an external debt to GDP of 22% and an External Debt $78 bl