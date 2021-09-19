# Explore-Weather-Trends

### Created by Akbarali Mukhammadiev
##### 02.09.2021

* [Extracting the data from the database using SQL](#Extracting-the-data-from-the-database-using-SQL)
* [Opening up the CSV and creating line charts](#Opening-up-the-CSV-and-creating-line-charts)
* [Observations](#Observations)

#### Extracting the data from the database using SQL. 
There was a workspace in the section that was connected to a database. I needed to export the temperature data for the world as well as for the closest big city to where I live. I found a list of cities and countries in the city_list table.
I wrote the following SQL query to extract the nearest city to my location: 

        SELECT * 
        FROM city_list 
        WHERE country LIKE 'Uzb%' 

In this way, I got only one result. 'Tashkent' was the only city that was included in the table. Therefore, I chose it as the closest city to my location. Next, to extract all the data realted to this city I wrote the following SQL query:

        SELECT year, avg_temp
        FROM city_data
        WHERE city = 'Tashkent'
        
Then, I exported the results to CSV and downloaded for analysing and creating a line chart.
Analogously, to extract all the temperature data for the world table, I simply wrote the following SQL query:

        SELECT *
        FROM global_data

Similarly, as in the case above, I exported the results to CSV and downloaded for analysing and creating a line chart.

#### 2. Opening up the CSV and creating line charts.
I opened the CSV files using Google sheets. Before plotting the line charts, I calculated the 10-year moving average in order to smooth out the lines and making trends more observable for each dataset that was extracted earlier. To calculate the moving average, I simply used the ready-made 'AVERAGE' function on Google Sheets. Initially, I chose AVERAGE(B2:B11) and then filled the remaining fields automatically. Next, I created line charts for each global and city level dataset putting 'year' on the horizontal axis and moving average temperature on the vertical axis. Then I put these two datasets together in order to create a general line chart that compares my city’s temperatures with the global temperatures. The correspoding line charts are on the following pages. 

#### 3. Observations.
Looking at the line chart that compares my city’s temperatures with the global one, I made the following observations about the similarities and differences between the world averages and my city’s averages, as well as overall trends:

* The average temperature in my city has always been higher than the world temperature for the entire period.
* The difference has always been consistent over time and the temperature started increasing sharply in my city from the mid 70s. 
* During this period, the coldest temperature in the world was at 1898, whereas in my city it was at the beginning of the period.
* So far, the highest temperature in the world was at the end of the period for the world and for my city as well. 
* The overall trend for both in the world and in my city is increasing. The world is getting hotter slowly, especially in the last two decades. 
