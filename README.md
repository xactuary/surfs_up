# surfs_up
# Analysis of Weather Data in Hawaii
## SUMMARY
This analysis compares the weather conditions in Hawaii in June and December.  The object is to see if the weather in Hawaii is conducive to surfing year round so that a surf and ice cream shop business would be sustainable with customers all year. 
###  BACKGROUND  


#### DATA PROVIDED  
- sqlite database of Hawaii Dates and Weather Variables
- Within the database is a table of weather Stations which contains the following variables:
1. id
2. station
3. name
4. latitude
5. longitude
6. elevation
- The table used for this analysis is Measurement which contains these variables:  
1. id
2. station
3. date
4. prcp  
5. tobs


  
### METHODOLOGY

The data provided is in an sqlite database which can be used on a local machine to do analytics without having to set up a server.  Using Python, Pandas and Sqlalchemy in a Jupyter notebook, data for the month of June for the years 2010-2017 was filtered out using the following code:
  
  `results = session.query(Measurement.date,Measurement.tobs).filter(extract('month', Measurement.date)==6)`
  
After translating the data into a list and pandas dataframe, descriptive statistics of this list were created using:
  
`dfjune.describe()`
  
#### JUNE WEATHER STATISTICS 
![](https://github.com/xactuary/surfs_up/blob/main/Resources/June_stats.PNG)  
  
Similar coding was used to develop the following statistics for the month of December:
  
#### DECEMBER WEATHER STATISTICS
![](https://github.com/xactuary/surfs_up/blob/main/Resources/Dec_stats.PNG)
  
### ANALYSIS OF RESULTS
An examination of the statistics indicates that the weather in December is on average 4 degrees cooler than in June.  However, the average temperature being 71 degrees in December is still acceptable for selling ice cream and surfing.  The range of temperatures is also slightly cooler in December than in June with the 25% in December being 69 degrees and in June it only goes down to 73. This means that only 25% of the time we would expecte temperatures to be below 69 degrees in December which is a very acceptable temperature for selling ice cream and surfing.  The absolute low temperature in December is 56 degrees which is a little chilly but does not happen very often.  Interestingly, the high temperature for June and December are only 2 points apart at 85 degrees versus 83 degrees.  Both of these are excellent ice cream selling temperatures.  Overall the statistics suggest that it is a reasonble business proposition to consider opening a year round ice cream and surf shop in Hawaii.  
  
In summary, the three key differences between the weather in June and December are:
1.  There is a higher average temperature in June than December by 4 points.
2.  The High temperature for June and December are within 2 points of each other at 83 degrees and 85 degrees
3.  The low temperature and 25% 
  
There are additional conditions that might be queried to help solidify the decision making for this task.  These queries might include:
  
  1.  Finding out average water temperature.  The data for this is not in our database but this would be worth gathering elsewhere to determine swimming and surfing conditions.
  2.  What is the average daily precipitation in these months.  This could be queried from this database.  If there is significant expected precipitation in any time period, that might mean lower ice cream sales.  
 

  
