# Predicting the Best Subway Station to Engage Tech Professionals for the WTWY Gala 

Sabrina Yang


## Abstract

The purpose of this project is to determine the best subway station that would allow WTWY to engage the highest number of interested tech professionals during their daily commutes. This would allow WTWY to give free gala tickets to people who will attend the event and help build awareness and reach for the organization. As budget is likely a consideration for WTWY, as it is for any organization, the station with the highest foot traffic and highest concentration of tech professionals would be most efficient for WTWY’s goals. I worked with the turnstile data provided by the [New York City MTA](http://web.mta.info/developers/turnstile.html) and applied multiple tools/analyses including SQL, numpy, and pandas. After running the analyses, I determined the most efficient placement plan for WTWY, at the subway station that would maximize tech professional foot traffic. 




## Design
The project’s goal is to help the WTWY optimize the effectiveness of their street team in soliciting tech professionals to attend the gala and spread awareness. The turnstile data provided by the MTA was analyzed by foot traffic, identifying the top stations. From this station list, the next layer of analysis was establishing where the major technology companies were concentrated in the city. These two factors together would maximize the number of tech professionals that the street teams would come across. 
  

## Data

The dataset contains 2299530 rows with 11 features for each, 2 of which are numerical and will be the focal points of this analysis. The time period of the data is the most recent 3 months, from February 28 2021 to May 14 2021. Some of the features included in the analyses are entries, exits, time, and dates. The following are some characteristics of the features:

 -  __Exits__: 	The cumulative exit register value for a device
 -  __Entries__: The cumulative entry register value for a device
 -  __Date__: Represents the date in (MM-DD-YY) format
 - __Time__ : Represents the time (hh:mm:ss) for a scheduled audit event, which is 4 hours in length

 
## Algorithms
#### *Data Manipulation and Exploratory Data Analysis*

1.	Cleaned data and removed duplicate entries, which repeat in the same turnstile and were possibly created by human error (*regular/recover aud under DESC column*)
2.	Calculated the difference between the cumulative entries and exits and converted to a daily/hourly unit, which included writing a function to reverse incorrect records
3.	Defined Daily Activity as the sum of entries and exits and is used as the main unit of measure
4.	Analyzed daily activity by weeks and determined that weekdays have higher foot traffic than weekends. Within the weekdays, Fridays were the highest
5.	Listed the top 20 stations with highest foot traffic by calculating the daily activity for all stations
6.	Filtered the top 20 stations using the NYC major tech firms map; the top 3 stations were 34th Street Penn Station, 24th Street Herald Square, and 23rd Street
7.	By analyzing hourly activity on Fridays at 34th Street Penn Station, the optimal time period was determined to be 6pm


## Tools
 -  Numpy and Pandas for data manipulation
 -  Matplotlib and Seaborn for plotting
 -  SQL for data extraction

## Communication
The results of the analyses will be communicated via data visualization in a PowerPoint presentation and the github will be provided for an in-depth view of the code utilized.



<img src="https://github.com/SYNYC/1_Project_MTA/blob/master/charts/all%20station-weekly%20average.png" width = "450" height = "305">

<img src="https://github.com/SYNYC/1_Project_MTA/blob/master/charts/all_station.png" width = "600" height = "305">

<img src="https://github.com/SYNYC/1_Project_MTA/blob/master/charts/Top20_tech.png.png" width = "600" height = "305">

<img src="https://github.com/SYNYC/1_Project_MTA/blob/master/charts/Hour_34Penn.png" width = "600" height = "305">

