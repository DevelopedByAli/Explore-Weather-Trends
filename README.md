# Explore-Weather-Trends

### Created by Akbarali Mukhammadiev
##### 02.09.2021

#### 1. Extracting the data from the database using SQL. 
There was a workspace in the section that was connected to a database. I needed to export the temperature data for the world as well as for the closest big city to where I live. I found a list of cities and countries in the city_list table.
I wrote the following SQL query to extract the nearest city to my location: 

        SELECT * 
        FROM city_list 
        WHERE country LIKE 'Uzb%' 

In this way, I got only one result. The closest city to my location is Tashkent. Next, to extract all the data realted to this city I wrote the following SQL query:

        SELECT year, avg_temp
        FROM city_data
        WHERE city = 'Tashkent'
        
Then, I exported the results to CSV and downloaded for analysing and creating a line chart.
Analogously, to extract all the temperature data for the world, I simply wrote the following SQL query:

        SELECT *
        FROM global_data

Similarly as in the case above, I exported the results to CSV and downloaded for analysing and creating a line chart.

#### 2. Opening up the CSV and creating line charts
I opened the CSV files using Google sheets. Above all, before plotting the line charts, I calculated the 10-year moving average for each dataset that extracted earlier in order to smooth out the lines, making trends more observable. In order to calculate the moving average, I simply used the ready made 'AVERAGE' function. Initially, I chose AVERAGE(B2:B11) and then filled the remaining fields automatically. Next, I created line charts for each global and city level dataset putting 'year' on the horizontal axis and moving average temperature on the vertical axis. Then I added up two datasets and created a general line chart that compares my city’s temperatures with the global temperatures.
