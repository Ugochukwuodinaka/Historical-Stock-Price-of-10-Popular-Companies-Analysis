# Historical Stock Price Of 10-Popular Companies (2015-2021) Analysis
![](images/Historical_Stock_Price_Of_10_Popular_Companies_image.jpg)
<br />

## Table of Contents
- [Project Overview](#project-overview)
- [About The Dataset](#about-the-dataset)
- [Tools Used](#tools-used)
- [Visualization in Power BI](#visualization-in-power-bi)
- [Project Analysis](#project-analysis)
- [Visuals in Power BI Report](#visuals-in-power-bi-report)
- [5 Strategies These 10 Companies May Need To Implement To Grow Their Stock Prices](#5-strategies-these-10-companies-may-need-to-implement-to-grow-their-stock-prices)
<br />

## Project Overview
### Introduction:
In the realm of finance, historical stock price analysis is indispensable for informed decision-making. This project delves into the historical stock prices of ten prominent companies globally: Apple, Amazon, Netflix, Microsoft, Google, Facebook, Tesla, Walmart, Uber, and Zoom. By scrutinizing their stock price data, the project aims to extract insights crucial for investors, analysts, and stakeholders.

### Objective:
The goals for this analysis project are as follows:
- __Total Traded Volume:__ Calculate the volume of shares for each of the ten companies traded during this period.
- __Total Volume Traded Quarterly:__ The trend analysis in relation to the total volume traded by the ten companies on a quarter-on-quarter basis gives insight into their trading activities over the year.
- __Average Low and High Price:__ It will calculate the average low and high prices that each stock of the company exchanged for, hence giving the price range in which these stocks have been traded.
- __Total Volume Traded by Year:__ This chart shows the trend of the total trading volume of stocks for each of the ten companies, outlining the trading dynamics for each over time.
- __Total Close Price by Year:__ The trend of the total closing prices of all stocks traded by the ten companies on a yearly basis will help the user see the overall trends in performance and valuation.

### Expected Findings:
- __Total Traded Volume:__ This can indicate whether total traded volumes are trending over time and therefore point to a change in investor sentiment or market dynamics, or that some company-specific event has occurred. High trading volumes could suggest precisely greater interest from investors or volatility in the stock.
- __Total Volume Traded Quarterly:__ This will pick up seasonal or other periodic fluctuations in the level of activity. This may include, for instance, spikes in trading volume in certain quarters that may correspond to the timing of earnings announcements or some other important news events.
- __Average Low and High Price:__ Knowing the average low and high prices will give one a feel for the range in which a stock commonly trades. Huge variations from this may present possible buying or selling opportunities.
- __Total Volume Traded by Year:__ Long-term trends in total volumes may indicate to the investor whether there is an interest in the stocks of these companies to investors in general. It is the tectonic shifts in trading volumes that characterize changes in sentiment or a change in how the company's fundamentals are valued by the market.
- __Total Close Price by Year:__ Long-term Analysis—The total closing prices may indicate a trend in the overall performance of the companies' stocks. Either an increasing or decreasing total close price might point to changes in the valuation by the market, investor expectations, or even in the performance of the companies themselves.
<br />
<br />

### About The Dataset
The dataset has 10 tables for the historical stock price data of 10 different companies. The data is provided by Quantum Analytics. Here is the link to the raw data folder; you can click here to find the transformed data folder. Now, for all these 10 tables, the column setup remains exactly the same.

All of the 10 tables has 7 columns each of the same column names and data types. Given below is the description of the 7 columns in the 10 tables that make up the dataset for this analysis project:
| Table                              | Field                    | Description                            |            
|:-----------------------------------|:------------------------ |:-------------------------------------- |
| Amazon.csv, Apple.csv, Facebook.csv, Google.csv, Microsoft.csv, Netflix.csv, Tesla.csv, Uber.csv, Walmart.csv, Zoom.csv| Date                     | This column shows the date of record or reporting of stock price data. Here, every row corresponds to each day in the dataset.    |
|                                    | Open                     | This is the open price of a security or the price it began selling for when the market opened on any given day of trading. It is the first quoted price for such security on that particular day.     |
|                                    | High                     | The highest price traded by that security on an official trading day. This is also referred to as the peak price that has been reached by security on that day.        |
|                                    | Low                      | The price of "Low" is the lowest that the stock has traded for during the trading day. It just depicts the lowest price touched by the stock on that particular day.         |
|                                    | Close                    | The price of "Close" is always the last price at which the stock closed when the market closes on a particular trading day. It's just the last price of the trade conducted on that day for that particular stock.        |
|                                    | Adjusted close           | "Adjusted Close" pricing refers to the close price of a stock at any given time; however, it readjusts for corporate actions that have taken place since its issue. This helps give a more distinctive, true value of the stock price.        |
|                                    | Volume                   | This column indicates the total number of shares of a given stock that traded during the trading day. Essentially, it is the level of trading activity of that particular stock for the day.        |
<br />
<br />

### Skills Utilized
1. Data Cleaning
2. Data Modelling
3. Data Visualiziation
4. Descriptive Analytics
5. Analytical and Critical Thinking
6. Problem Solving
7. Communication and Reporting
<br />

### Tools Used
1. Power Query Editor
    - Was used to:
        1. Extract,
        2. Cleaned
        3. Transform  all the datasets for this analysis.
           
2. Power BI (Was used to create reports and dashboard for this analysis)
    - The following Power BI Features were incorporated:
        1. DAX
        2. Quick Measures
        3. Filters
        4. Tooltips
<br />

### Data Cleaning, Transformation and Loading using the Power Query Editor:
1. Added the column __"Company"__ in each of the 10 tables to reflect the names of each company in their individual data table.
2. Created a new table __"Company Lookup"__ with only one column: __"Company"__ to be able to relate with all the other tables with the "Company" key.
3. Created a new table __"10 Companies"__ housing all the data in each and every of the dataset table columns.
4. Created a table __"Date Year"__ to house the __"Date"__ seperately.
5. Added a new column __"Quarter"__ in the __"10 Companies"__ table to handle stock transactions by the 4 quaters of the year.
6. Transformed every other column type to its appropriate column type.
7. After data cleaning and tranformation were performed on all the tables. The tables appeared to be clean. The quality of each column became 100% valid with zero errors or nulls.

- Below is a preview of some of the tables which are __Amazon__, __Facebook__, __Microsoft__, __Tesla__, and __10 Companies__ tables:


Amazon Table                                               | Facebook Table        
:---------------------------------------------------------:|:--------------------------------------------:|
![](images/Amazon_table_Power_Query.png)                          | ![](images/Facebook_table_Power_Query.png)


Microsoft Table                                            |Tesla Table
:---------------------------------------------------------:|:------------------------------------------------------:|
![](images/Microsoft_table_Power_Query.png)                       |![](images/Tesla_table_Power_Query.png)  
                  
10 Companies Table                                                                 |                                
:---------------------------------------------------------------------------------:|
![](images/10_Companies_table_Power_Query.png)                                            |                                
<br />
<br />

## Data Model Design
The data required for this analysis are located in various tables. Therefore, data modelling was required. A star Schema was designed with the Company_Lookup table representing the __dimension table__ containing all the company names, and to which other __fact tables__ were modelled or connected, using the __Company__ column that is common amongst them. The __Company Lookup__ table has been modelled with:

- __Amazon__ table using the __"Company"__
- __Apple__ table using the __"Company"__
- __Facebook__ table using the __"Company"__
- __Google__ table using the __"Company"__
- __Microsoft__ table using the __"Company"__
- __Netflix__ table using the __"Company"__
- __Tesla__ table using the __"Company"__
- __Uber__ table using the __"Company"__
- __Walmart__ table using the __"Company"__
- __Zoom__ table using the __"Company"__
- __10 Companies__ table using the __"Company"__

The __Date Year__  table also has a relationship with the fact tables through a direct relationship with the __10 Companies__ tables using the key column __"Date"__ in both the __Date Year__ table and the __10 Companies__ table.
- Because our screenshot couldn't contain all the tables and their relationships, I divided the view into 2. The __Model View 1__ displays all the 10 Company fact tables linked to the dimension table,
- __Model View 2__ displays a view of the __Company Lookup__ (dimension) table, the __10 Companies__ table (fact) table, the __Date Year__ table linked to the __10 Company's__ table, the 10 Companies table linked to the __Company Lookup__ table and the __Data Analysis Expression__ (DAX) standing alone.  You can access the full Power BI project document [here](HISTORICAL%20STOCK%20PRICE%20OF%2010%20POPULAR%20COMPANIES.pbix).
<br />

Model View 1 (For all 10 Companies)                                                |                                
:---------------------------------------------------------------------------------:|
![](images/Model_View_1.png)                                                              |           
<br />

Model View 2 (Showing the relationship between the fact tables and the dimension table)      |                                
:--------------------------------------------------------------------------------------------:|
![](images/Model_View_2.png)                                                                         |           
<br />
<br />

## Visualization in Power BI:
#### Report
![](images/Historical_Stock_Price_Of_10_Popular_Companies_Dashboard.jpg)
<br />
<br />

### Project Analysis:
From the analysis, i made the below Key findings:
- The Total Traded Volume: __465bn.__
- The Total Average Traded Volume: __28.25M.__
- Average Traded Open Price: __409.76.__
- Average Traded Close Price: __409.81.__
- Average Adjusted Close Price: __447.01.__
- The Total Number of Companies: __10.__
<br />
<br />

- <img src="images/Total_Traded_Volume_By_Company_image.jpg" width="250">

- **The Total Traded Volume By Company:**
My analysis OF thE total traded volume by a company brings out overwhelming disparities in trading activity among the ten popular companies. The conclusion shows that Apple leads in terms of volume traded, having 243 billion shares traded, followed by Tesla and Microsoft with 67 billion and 53 billion, respectively. Other companies, like Facebook, Netflix, Uber, Walmart, and Amazon, trade at volumes running from 39 to 15 billion shares in that order. Zoom and Google are completely out of this pace, with quite considerably lower total traded volumes of 4 billion and 3 billion shares, correspondingly.

- __My Interpretation and Insights:__
  - __Investor Interest and Market Dynamics:__
    - __High Volume Leaders__<br> Apple, Tesla, and Microsoft exhibit high volumes traded, which is indicative of strong investor interest and confidence.
    - __Market Trends__<br> Changes in volume traded mirror shifts in investor sentiment and market dynamics.
    - __Market Liquidity:__ With higher volumes, one expects better liquidity and price discovery, making these stock plays more interesting for the active trader.
  - __Company-Specific Events:__
    - __Effect of News on Price/Demand:__ This may include earnings reports, product launches, mergers, and the like.
    - __Examples:__
      - Tesla's volume may be the handiwork of its innovative products and a strong brand image.
      - Apple is probably in the lead because of the innovations it keeps introducing and sound economic performance.
  - __Volatility and Risk:__
      - __Volume and Volatility:__ An augmented volume of trade may be indicative of more volatility.
      - __Opportunities and Risks:__ As a simple matter of fact, volatility means potential gains or losses and presents both opportunities and risks for investors.
      - __Price Fluctuations:__ High trading volumes in the shares could result in further movements in the share price in the direction of market news, thus offering a number of trading opportunities in the short term.
<br />
<br />

- <img src="images/Total_Volume_Traded_By_Quarter_image.jpg" width="250">

- **Total Volume Traded By Quater:**
- In this case, the total volume that is traded quarterly will go a long way in bringing out the seasonal trends or fluctuations in market activity from the year 2015 to 2021. Since the data clearly reflects trends of the total trading volumes through the four quarters of a year, the first one, therefore, has the highest total volume traded, followed by Quarter 3, Quarter 2, and then finally Quarter 4.
  
- __Interpretation and Insights:__
  - __Seasonal Trends and Trading Activity:__
    - __Quarter 1:__ Increased trading volume from the combination of the following:
        – Annual earnings reports
        – Strategic investor planning
        – Portfolio rebalancing
    - __Quarter 2 & 3:__ Stable trading volume from:
        – Industry conferences
        - Economic data releases
        - Company-specific announcements
    - __Quarter 4:__ Slightly lower volume but still active due to:
        - Tax considerations
        - Holiday spending trends
        - End-of-year portfolio adjustments
        - Earnings Releases and Major Announcements:
  - __Earnings Releases__: Higher trading when companies post quarterly results.
    - __Major Events:__ Trading spikes due to product launches, mergers, acquisitions, or regulatory news.
    - __Investor Behavior and Market Sentiment:__
    - __Economic Conditions:__ Shifts in the economy lead to altered strategies for investors.
    - __Geopolitical Events:__ Political happenings change market sentiments.
  - __Industry Trends:___ Sectorial growth or decline impacts the behavior of investors.
<br />
<br />

- <img src="images/Average_Low_and_High_Price_Traded_By_Companies_image.jpg" width="500">

- **Total Average Low And Hhigh Price Traded By Company:**
  - __Price Range Understanding:__
  - The total average low and high prices that each company trades at can help investors to get an idea of where the stock typically falls. For example, examining the total average low and high prices for Amazon, one could say that this company mostly trades within a higher price range compared with other businesses like Uber or Apple. The average price will identify those stocks with high average lows and highs as being more valued or premium in nature, while those with low prices will be rated as more affordable or speculative. 
  - __Identifying Opportunities to Buy or Sell:__
  - Below- or above-average price extremes can be an indication to buy or sell for investors.
For instance, when its price plunges severely below the average low, it presents a buying opportunity to the investor who has cause to believe the stock has been beaten down and is due for a bounce. Conversely, when the price of a stock goes too high above the average high price, this could mean that the stock is becoming too expensive hence, a sell or take-profit signal. 
  - __Risk Assessment:__
  - One such knowledge that will bring out the risk associated with trading a particular stock is the average low and high prices that are traded by a company. The risk perception would be higher in stocks having a wider range of prices and lower for those with a narrower range of prices. 
<br />
<br />

- <img src="images/Total_Traded_Volume_By_Company_Year_Trend_image.jpg" width="500">

- **Total Traded Volume By Company Year Trend:**
  - __Overall Growth or Decline in Trading Volume:__ Across most companies, there is a general trend of increasing trading volume over the years, indicating growing investor interest in these stocks. For example, Amazon, Apple, Microsoft, and Tesla have experienced consistent growth in trading volume from 2015 to 2021. This upward trend in trading volume suggests a positive outlook towards these companies by investors over the long term. It may be attributed to factors such as company performance, industry trends, market dynamics, and macroeconomic conditions.
  - __Company-Specific Trends:__ Some companies exhibit fluctuations or irregularities in trading volume over the years. For instance, Uber and Zoom, being relatively newer companies, show significant increases in trading volume from 2019 onwards, reflecting heightened investor interest following their initial public offerings (IPOs). Netflix shows a slight decline in trading volume from 2015 to 2021, which could be attributed to factors such as increased competition in the streaming industry or changes in consumer preferences. However, the overall trend remains relatively stable.
  - __Indicators of Market Sentiment and Company Fundamentals:__ Significant changes in trading volume can be indicative of shifts in market sentiment or changes in company fundamentals. For example, sudden spikes in trading volume may coincide with major news events, earnings releases, product launches, or regulatory announcements that impact investor perceptions. Investors often interpret changes in trading volume as signals of market activity and adjust their investment strategies accordingly. Higher trading volumes may reflect increased investor confidence or speculation, while lower volumes may signal caution or lack of interest.
  - __Long-Term Investment Trends:__ The long-term trends in total traded volume provide valuable insights for investors seeking to understand the broader investment landscape and identify potential opportunities or risks. Companies with consistent growth in trading volume over the years may be viewed favorably by investors as stable investment options with strong growth prospects. Conversely, companies experiencing declining trading volume may face challenges or uncertainties that warrant closer

<br />
<br />

- <img src="images/Total_Close_Price_By_Company_Year_Trend_image.jpg" width="500">

- **Total Close Price By Company Year Trend:**
- This multi-line chart presents the total close price of each company's stock across the years 2015 to 2021. In this analysis, I aim to provide insights into the performance trends of the companies' stocks over time and how changes in total close prices may reflect shifts in market valuation, investor expectations, or company performance.
  - __My Interpretation and Insights:__
    - __Overall Performance Trends:__ The data shows different trends in the total close prices of each company's stock over the seven-year period. Some companies consistently have higher close prices, while others have more ups and downs. For example, Amazon, Apple, Facebook, Google, Microsoft, Netflix, Tesla, Walmart, Uber, and Zoom all have unique patterns in their total close prices over time because each company operates in its own way and faces different market conditions.
    - __Changes in Market Valuation and Investor Expectations:__ Increasing total close prices over time may mean that the market values the company more and investors are optimistic about its future. It suggests that investors are willing to pay more for the company's stock because they expect it to grow and make more money. On the other hand, decreasing total close prices may indicate that the market values the company less and investors are worried about its performance.
    - __Impact of Company Performance:__ Changes in total close prices can also show how well or poorly a company is doing. This includes things like changes in how much money it makes, its profits, its share of the market compared to competitors, or its plans for growth. Good news like strong financial results or successful new products can make stock prices go up, while bad news can make them go down. For example, Tesla's huge increase in total close price from 2015 to 2021 may be because it has been growing quickly, coming up with new ideas for technology, and getting more customers than other electric car companies.
    - __Investor Behavior and Market Dynamics:__ The way investors act and what's happening in the market also affect changes in total close prices over time. Things like how the economy is doing overall, trends in different industries, new rules from the government, or big events around the world can make investors feel more positive or negative and cause stock prices to move. Looking closely at what's really behind changes in total close prices helps investors make smart choices and change their investment plans to take advantage of good things or protect themselves from bad things.
<br />
<br />

## Visuals in Power BI Report:
You can view and interact with this dashboard report on Historical Stock Price of 10 Popular Companies (2015-2021) Analysis [here](https://app.powerbi.com/view?r=eyJrIjoiM2M4OGY4OWQtMzlmNS00OTljLTgyNGUtYTU2NmVmZjFjN2IyIiwidCI6IjdlYzI5NjU5LTNjZjItNGYzZi1hYmIzLWE3MjJlZGY3ZmYyZCJ9).
<br />
<br />
<br />

## 5 Strategies These 10 Companies May Need To Implement To Grow Their Stock Prices
- __Continuous Innovation:__ These 10 Companies may need to invest in research and development (R&D) to innovate and develop new products, services, or technologies that address emerging market needs and trends. Continuous innovation can enhance competitive advantage and drive revenue growth.
- __Market Expansion and Diversification:__ They may also need to explore opportunities for geographic expansion into new markets or diversification into adjacent industries or sectors. Expanding the customer base and revenue streams can mitigate risk and unlock new growth opportunities.
- __Digital Transformation:__ They would need to embrace digital transformation initiatives to leverage technology for enhanced operational efficiency, customer engagement, and data-driven decision-making. Investing in digital infrastructure and online platforms can drive growth in the digital economy.
- __Strong Financial Performance:__ It would be necessary they maintain strong financial performance by achieving revenue growth, profitability, and efficient capital allocation.
- __Transparency and Stakeholder Engagement:__ They may need to foster transparency, open communication, and stakeholder engagement with investors, employees, customers, and the community. Providing regular updates on company performance, and strategic initiatives can build trust and credibility, ultimately driving shareholder value.
<br />
<br />

## Thank You For Following Through!
![](images/hands-holding-words-thank-you.jpg)
