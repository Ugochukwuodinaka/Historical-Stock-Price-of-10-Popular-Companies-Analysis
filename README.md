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
- __Total Traded Volume:__ To calculate the volume of shares which each of the ten companies traded during this period.
- __Total Volume Traded Quarterly:__ To look into the trend analysis in relation to the total volume traded by the ten companies on a quarter-on-quarter basis which will give insight into their trading activities over the year.
- __Average Low and High Price:__ To calculate the average low and high prices that each stock of the company exchanged for, hence give the price range in which these stocks have been traded.
- __Total Volume Traded by Year:__ To use a chart to show the trend of the total trading volume of stocks for each of the ten companies, thereby outlining the trading dynamics for each over time.
- __Total Close Price by Year:__ To analyze The trend of the total closing prices of all stocks traded by the ten companies on a yearly basis which will help the users see the overall trends in performance and valuation.

### Expected Findings:
- __Total Traded Volume:__ This will unravel whether total traded volumes are trending over time and therefore point to a change in investor sentiment or market dynamics, or that some company-specific event has occurred. High trading volumes could suggest precisely greater interest from investors or volatility in the stock.
- __Total Volume Traded Quarterly:__ This will pick up seasonal or other periodic fluctuations in the level of activity. This may include, for instance, spikes in trading volume in certain quarters that may correspond to the timing of earnings announcements or some other important news events.
- __Average Low and High Price:__ Knowing the average low and high prices will give one a feel of the range in which a stock commonly trades. Huge variations from this may present possible buying or selling opportunities.
- __Total Volume Traded by Year:__ This will show long-term trends in total volumes which may indicate to the investor whether there is an interest in the stocks of these companies to investors in general. It is the tectonic shifts in trading volumes that characterize changes in sentiment or a change in how the company's fundamentals are valued by the market.
- __Total Close Price by Year:__ Long-term Analysis will be displayed. The total closing prices may indicate a trend in the overall performance of the companies' stocks. Either an increasing or decreasing total close price might point to changes in the valuation by the market, investor expectations, or even in the performance of the companies themselves.
<br />
<br />

### About The Dataset
The dataset has 10 tables for the historical stock price data of 10 different global companies. The data was provided by Quantum Analytics. [Here](Raw_Data) is the link to the raw data folder; you can click [here](ETL_Data) to find the transformed data folder. Now, for all these 10 tables, the column setup remains exactly the same.

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
        2. Clean and
        3. Transform all the datasets for this analysis.
           
2. Power BI (Was used to create reports and dashboard for this analysis)
    - The following Power BI Features were incorporated:
        1. DAX
        2. Quick Measures
        3. Filters
        4. Tooltips
<br />

### Data Cleaning, Transformation and Loading using the Power Query Editor:
1. Added the column __"Company"__ in each of the 10 tables to reflect the names of each company in their individual data table.
2. Created a new table __"Company Lookup"__ with only one column: __"Company"__ which was enabled to relate with all the other tables through the "Company" key.
3. Created a new table __"10 Companies"__ housing the entire table data in each and every of the dataset table columns.
4. Created a table __"Date Year"__ to house the __"Date"__ seperately.
5. Added a new column __"Quarter"__ in the __"10 Companies"__ table to handle stock transactions by the 4 quarters of the year.
6. Transformed every other column type to its appropriate column type.
7. After data cleaning and tranformation were performed on all the tables. The tables appeared to be clean. The quality of each column became 100% valid with zero errors or nulls.

- Below is a preview of some of the tables which are __Amazon__, __Facebook__, __Microsoft__, __Tesla__, and the __10 Companies__ tables:


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
The data required for this analysis are located in various tables. Therefore, data modelling was required. A star Schema was designed with the Company_Lookup table representing the __dimension table__ containing all the company names, and to which other __fact tables__ were modelled or connected to using the __Company__ column that was common amongst them. The __Company Lookup__ table has been modelled with:

- __Amazon__ table using the __"Company"__ column.
- __Apple__ table using the __"Company"__ column.
- __Facebook__ table using the __"Company"__ column.
- __Google__ table using the __"Company"__ column.
- __Microsoft__ table using the __"Company"__ column.
- __Netflix__ table using the __"Company"__ column.
- __Tesla__ table using the __"Company"__ column.
- __Uber__ table using the __"Company"__ column.
- __Walmart__ table using the __"Company"__ column.
- __Zoom__ table using the __"Company"__ column.
- __10 Companies__ table using the __"Company"__ column.

The __Date Year__  table also has a relationship with the fact tables through a direct relationship with the __10 Companies__ table using the key column __"Date"__ in both the __Date Year__ table and the __10 Companies__ table.
- Because our screenshot couldn't contain all the tables and their relationships at once, I divided the view into 2. The __Model View 1__ displays all the 10 different Company fact tables linked to the dimension table.
- __Model View 2__ displays a view of the __Company Lookup__ (dimension) table, the __10 Companies__ table (fact) table, the __Date Year__ table linked to the __10 Company's__ table, the 10 Companies table linked to the __Company Lookup__ table, and the __Data Analysis Expression__ (DAX) standing alone.  You can access the full Power BI project document [here](HISTORICAL%20STOCK%20PRICE%20OF%2010%20POPULAR%20COMPANIES.pbix).
<br />

Model View 1 (For all the 10 Companies)                                                |                                
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
My analysis oF the total traded volume by company brings out overwhelming disparities in trading activity among the ten popular companies. The conclusion shows that Apple leads in terms of volume traded, having 243 billion shares traded, followed by Tesla and Microsoft with 67 billion and 53 billion, respectively. Other companies, like Facebook, Netflix, Uber, Walmart, and Amazon, trade at volumes running from 39 to 15 billion shares in that order. Zoom and Google are completely out of this pace, with quite considerably lower total traded volumes of 4 billion and 3 billion shares, correspondingly.

- __My Interpretation and Insights:__
  - __Investor Interest and Market Dynamics:__
    - __High Volume Leaders:__ Apple, Tesla, and Microsoft exhibit high volumes traded, which is indicative of strong investor interest and confidence.
    - __Market Trends:__ Changes in volume traded mirror shifts in investor sentiment and market dynamics.
    - __Market Liquidity:__ With higher volumes, one expects better liquidity and price discovery, making these stocks play more interesting role for the active trader.
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
    - __Quarter 1:__ Increased trading volume which may be as a result of the combination of the following:
        – Annual earnings reports
        – Strategic investor planning
        – Portfolio rebalancing
    - __Quarter 2 & 3:__ Stable trading volume which may be likely from:
        – Industry conferences
        - Economic data releases
        - Company-specific announcements
    - __Quarter 4:__ Slightly lower volume but still active which may be due to:
        - Tax considerations
        - Holiday spending trends
        - End-of-year portfolio adjustments
        - Earnings Releases and Major Announcements:
  - __Earnings Releases__: Higher trading may occur when companies post quarterly results.
    - __Major Events:__ Trading spikes due to product launches, mergers, acquisitions, or regulatory news.
    - __Investor Behavior and Market Sentiment:__
    - __Economic Conditions:__ Shifts in the economy may lead to altered strategies for investors.
    - __Geopolitical Events:__ Political happenings can change market sentiments.
  - __Industry Trends:___ Sectorial growth or decline may impacts the behavior of investors.
<br />
<br />

- <img src="images/Average_Low_and_High_Price_Traded_By_Companies_image.jpg" width="500">

- **Total Average Low And Hhigh Price Traded By Company:**
  - __Price Range Understanding:__
  - The total average low and high prices that each company trades at can help investors to get an idea of where the stock typically falls. For example, examining the total average low and high prices for Amazon, one could say that this company mostly trades within a higher price range compared with other businesses like Uber or Apple. The average price will identify those stocks with high average lows and highs as being more valued or premium in nature, while those with low prices will be rated as more affordable or speculative. 
  - __Identifying Opportunities to Buy or Sell:__
  - Below or above average price extremes can be an indication to buy or sell for investors.
For instance, when its price plunges severely below the average low, it presents a buying opportunity to the investor who has cause to believe the stock has been beaten down and is due for a bounce. Conversely, when the price of a stock goes too high above the average high price, this could mean that the stock is becoming too expensive hence, a sell or take-profit signal. 
  - __Risk Assessment:__
  - One such knowledge that will bring out the risk associated with trading a particular stock is the average low and high prices that are traded by a company. The risk perception would be higher in stocks having a wider range of prices and lower for those with a narrower range of prices. 
<br />
<br />

- <img src="images/Total_Traded_Volume_By_Company_Year_Trend_image.jpg" width="500">

- **Total Traded Volume By Company Year Trend:**
  - __Overall Growth or Decline in Trading Volume:__ For most firms, the general trend is an increased trading volume over the years, showing investors' increasing interest in such kinds of stocks. For example, Amazon, Apple, Microsoft, and Tesla had a continuous growth in trading volumes from 2015 to 2021. This upward trend of trading volume reflects that the investors are looking positively towards these companies in the long term. This can be attributed to company performance, industry trends, market dynamics, and macroeconomic conditions. 
  - __Company-Specific Trends:__ Some companies show fluctuations or irregularities in trading volume over the years. For example, Uber and Zoom have huge trading volume increases upwards from 2019, this corresponds to the increasing interest of investors post the IPO events. In the case of Netflix, there is a slight decline in trading volume from 2015 up to 2021. The reason could be that more and more players entered into the streaming business or that consumer tastes changed. However, the overall trend remains quite flat. 
  - __Market Sentiment and Company Fundamentals Indicators:__ The indicating change in the Market Sentiments/Company Fundamentals, substantial change in the trading volume of the shares is usually affected now and then. For example company's result announcements, or any other major news, critical regulatory or policy changes that affect the thinking of the investors may cause a sharp surge in trading volume. Changes in trading volume are interpreted by investors themselves as a signal to or of market activity, in which investment strategies are, therefore, changed accordingly. Higher trading volumes may reflect an increase in investor confidence or speculation, while lower ones may piggyback caution or lack of interest. 
  - __Long-Term Investment Trends:__ Long-term trends in total traded volume give valuable insights to investors looking to understand the bigger picture of investments to visualize trends, opportunities, or risks. Businesses whose trading volumes have been increasing consistently over the years may be considered by investors as very stable companies in terms of investment with good growth prospects. Companies that record falling volumes of trade could be facing some challenges or uncertainties that call for a closer look.
<br />
<br />

- <img src="images/Total_Close_Price_By_Company_Year_Trend_image.jpg" width="500">

- **Total Close Price By Company Year Trend:**
- The multiple-line chart indicates the total close prices for each stock of the companies over the years from 2015 to 2021. In relation to this, I tried to provide some insight into companies' stock performance trends over time and how changes in total close prices may be driven by changes in market valuations, investor expectations, or company performance.
- __My Interpretation and Insights:__
   - __Overall Performance Trends:__ From the data, one can see the various trends that each of the companies' stock has taken within the seven years. While some companies show a higher close price compared to others, some have more ups and downs. For example, Amazon, Apple, Facebook, Google, Microsoft, Netflix, Tesla, Walmart, Uber, and Zoom, all have their total close prices specified over time because each company is different in its business and experiences different market conditions.
   - __Changes in Market Valuation and Investor Expectations:__ In a situation where the series of total close prices is increasing over time, then it would means that the market may hold a company{s} in higher regard and investors may become more optimistic about the company's future. That means investors are ready to pay more for the company's share since they believe in its growth and more money will be invested as more shares will be traded. On the other hand, if there had been a drop in the total closing price, then one could assume that less value was put on the firm by the market, and normally, the investors become worried over its performance.
   - __Company Performance Effects:__ Total close price movements may be driven by how well or how bad the company is doing. These include such factors as changes in revenues, profitability, market share, and growth plans versus competition. Good news, such as solid financial results or successful new products, may drive stock prices up, and bad news may drive them down. For example, Tesla's total close price increased significantly from 2015 to 2021, which might be due to its fast growth and new ideas in technology, hence attracting more customers as compared to other electric car companies.
   - __Investor behavior and market dynamics:__ The changes in aggregate closing prices over time are driven by the attitude and actions taken by investors, along with what is going on in the market. This could involve the general state of the economy, sectors, new government rules and regulations, or major global events that raise or lower investor sentiment, hence driving stock prices. Knowing what exactly makes total close price changes can, therefore, help investors to make informed decisions and adjust their investment plans accordingly so that they can take advantage of positive market situations or keep away from negative market trends.
<br />
<br />

## Visuals in Power BI Report:
You can view and interact with this dashboard report on Historical Stock Price of 10 Popular Companies (2015-2021) Analysis [here](https://app.powerbi.com/view?r=eyJrIjoiM2M4OGY4OWQtMzlmNS00OTljLTgyNGUtYTU2NmVmZjFjN2IyIiwidCI6IjdlYzI5NjU5LTNjZjItNGYzZi1hYmIzLWE3MjJlZGY3ZmYyZCJ9).
<br />
<br />
<br />

## 5 Strategies These 10 Companies May Need To Implement To Grow Their Stock Prices
- __Innovate Continuously:__ These 10 Companies may be looking to invest in research and development for innovating and developing new products, services, or technologies that will quench the emerging market needs and trends. Innovation continuously enhances competitive advantage and allows revenue growth.
- __Geographical Expansion:__ They may also wish to point out opportunities for geographic expansion into new markets, or diversification into adjacent industries and sectors. Customer base growth and source diversification can decrease risk, unlock new growth, and create entirely new opportunities for development.
- __Digital Transformation:__ They would have to initiate digital transformation processes in order to make use of technology in improving operational efficiency, engaging customers, and making data-driven decisions. Digital infrastructure and online platforms can spur growth within the digital economy.
- __Strong Financial Performance:__ It would be important that they maintain strong financial performance concerning revenue growth, profitability, and efficient capital allocation.
- __Transparency and Stakeholder Engagement:__ Establish transparency, openness in communication, and engagement with stakeholders, investors, employees, customers, and the community. There could be a culture of trust, credibility, and value to shareholders with regular updates with company performance and strategic initiatives.
<br />
<br />

## Thank You For Following Through!
![](images/hands-holding-words-thank-you.jpg)
