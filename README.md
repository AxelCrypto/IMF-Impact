# Impact of IMF on Developping Countries

#### What is the impact of IMF loans towards borrowers' GDP and Poverty Statistics. 

## Database Creation 📋

### I. IMF Database creation
#### Objective: Download a CSV of data from developping countries with GDP and Poverty indicators as well as IMF loans figures.  

~ Step 1: From the WorldBank.org I downloaded the usefull data.
- I selected all countries from south Asia, Latine America and Africa. 
- I selected the entire time horizon available: 1970 to 2021.
- I had access to 1442 indicators. I exctacted a short list of indicators coming from only two categories: 
  - Economic Policy & Debt
  - Poverty  
    - This was still 411 lines of data per country. I reviewed every line and decided to keep a short list of 40 indicators per country.


~ Step 2: Database cleaning (columns names, nulls, typos and types of data)

![series](https://github.com/AxelCrypto/IMF-Impact/Images/series.png)


### II. Exterior Debt to GDP per country 
#### Objective: What is the international borrowing situation of IMF borrowers ?  
In addition to the evolution of GDP and poverties indicators for each country financed by the IMF, knowing its debt % towards external countries in comparation to its GDP would be an interesting additional indicator.

![debt](https://github.com/AxelCrypto/IMF-Impact/Images/debt.png)


~ Step 1: Collect the data from https://en.wikipedia.org/wiki/List_of_countries_by_external_debt  
Use of BeautifulSoup.   
~ Step 2: Clean the data and export it to a DataFrame  
~ Step 3: Link the Data to the IMF DataFrame through a primary key "id_Name".  

### III. Credit Rating
#### Objective: Credits are not free. Neither are the ones accorded by IMF or the World Bank. Interest rates are often influenced by the nation's credit rating. How tend to be rated IMF borrowers ?   
~ Step 1: Using Selenium I extracted the ratings from: https://tradingeconomics.com/country-list/rating  
~ Step 2: Clean the data and export it to a DataFrame    
~ Step 3: Link the Data to the IMF DataFrame through a primary key "id_Rating".  

![ratings](https://github.com/AxelCrypto/IMF-Impact/Images/ratings.png)





