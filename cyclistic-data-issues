

#Cyclistic Case Study:Data Issues in SQL
###Vincent Liu

This is documentation to describe data issues that I noticed from the [Cyclistic public data](https://divvy-tripdata.s3.amazonaws.com/index.html) in SQL.

##Data Issues

1. Some rows have empty *start_station_id*.

``` sql
SELECT START_STATION_NAME, START_LAT, START_LNG, COUNT(*) FROM BIKE_HISTORY2
WHERE START_STATION_NAME IS NULL 
```

2. Some rows have empty *end_station_id*
  
``` sql
SELECT START_STATION_NAME, START_LAT, START_LNG, COUNT(*) FROM BIKE_HISTORY2
WHERE END_STATION_NAME IS NULL
```

3. Some rows have **both** empty *start_station_id* and *end_station_id*. 

``` sql
SELECT START_STATION_NAME, START_LAT, START_LNG, COUNT(*) FROM BIKE_HISTORY2
WHERE START_STATION_NAME IS NULL 
AND END_STATION_NAME IS NULL
```

4. Some rows have *ended_time* earlier than the *started_time*.

``` sql
SELECT START_STATION_NAME, START_LAT, START_LNG, COUNT(*) FROM BIKE_HISTORY2
WHERE STARTED_AT < ENDED_AT
```


  


