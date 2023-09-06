## Cyclistic Case Study: Data Cleaning in RStudio
# Vincent Liu

This is documentation to describe the data cleaning process for the Cyclistic Bike Case Study as a part of the Google Data Analytics Certificate. 

I used RStudio to clean and append the data together. I will use Cyclistic’s historical bike trip data from August 2022 to July 2023, which is publicly available by clicking [here](https://divvy-tripdata.s3.amazonaws.com/index.html). The Cyclistic Data is available on a month to month basis, with each month’s information stored in its own CSV file.

The data includes Ride ID, user type, bike type, and start & end details (times, positions, station names).

I will first load the packages required for the data cleaning process. 

```{r}
library(tidyverse) #for wrangling data
library(lubridate) #for wrangling data attributes
library(readr) #for uploading data 
```

Next, I will upload the CSV files I have downloaded from each month into a dataframe in R.  
```{r}
m7_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202307-divvy-tripdata.csv")
m6_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202306-divvy-tripdata.csv")
m5_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202305-divvy-tripdata.csv")
m4_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202304-divvy-tripdata.csv")
m3_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202303-divvy-tripdata.csv")
m2_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202302-divvy-tripdata.csv")
m1_2023 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202301-divvy-tripdata.csv")
m12_2022 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202212-divvy-tripdata.csv")
m11_2022 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202211-divvy-tripdata.csv")
m10_2022 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202210-divvy-tripdata.csv")
m9_2022 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202209-divvy-publictripdata.csv")
m8_2022 <- read_csv("C:/Users/vliu1/Desktop/Google Case Study (Divvy)/202208-divvy-tripdata.csv")
```


I will drop the columns from each dataframe that will not be necessary for our analysis, such as start and end station ID as Ill as ride IDs (*start_station_id*, *end_station_id*, *ride_id*).
```{r}
m7_2023 <- m7_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m6_2023 <- m6_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m5_2023 <- m5_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m4_2023 <- m4_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m3_2023 <- m3_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m2_2023 <- m2_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m1_2023 <- m1_2023 %>% select (-c(start_station_id, end_station_id, ride_id))
m12_2022 <- m12_2022 %>% select (-c(start_station_id, end_station_id, ride_id))
m11_2022 <- m11_2022 %>% select (-c(start_station_id, end_station_id, ride_id))
m10_2022 <- m10_2022 %>% select (-c(start_station_id, end_station_id, ride_id))
m9_2022 <- m9_2022 %>% select (-c(start_station_id, end_station_id, ride_id))
m8_2022 <- m8_2022 %>% select (-c(start_station_id, end_station_id, ride_id))
```

Now I will combine each dataframe into one. 
```{r}
total_trips <- bind_rows (m7_2023, m6_2023, m5_2023, m4_2023, m3_2023, m2_2023, m1_2023, m12_2022,m11_2022,m10_2022,m9_2022,m8_2022)
```

I will check if the data is correct. The *member_casual* column should only have casual or member output, and the *rideable_type* column should only have classic bike, docked bike, or electric bike.

```{r}
table(total_trips$member_casual) #should only be casual or member
table(total_trips$rideable_type) #should only result in classic bike, docked bike, or electric bike
```

Next, I will format the dates into months, year, and day of the week. 

```{r}
total_trips$date <- as.Date(total_trips$started_at)
total_trips$month <- format(as.Date(total_trips$date), "%m")
total_trips$year <- format(as.Date(total_trips$date), "%Y")
total_trips$day_of_week <- format(as.Date(total_trips$date), "%A")
```

Finally, the dataframe is ready for analysis. I will convert the dataframe into a .csv file on my local directory. 

```{r}
write.csv(total_trips, "overall-trips.csv", row.names = FALSE)
```
