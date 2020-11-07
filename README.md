# surfs_up
# Analysis of Weather data in Hawaii
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


  
