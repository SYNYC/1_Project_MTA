# Project 1  MTA   
## _Project Proposal_


## Question & need:

##### What is the framing question of your analysis, or the purpose of the model/system you plan to build?
  
The purpose of the model I built is to determine the top 10 stations by foot traffic, in order to best place our client’s, WTWY, street teams.

##### Who benefits from exploring this question or building this model/system?

Our client can benefit from this model by developing the most efficient placement plan at the top most busy stations while accounting for their specific workforce budget, which includes the ideal work hours on weekdays and weekends for gathering the most signatures/contact info.



## Data Description:

##### What dataset(s) do you plan to use, and how will you obtain the data?
  - Resource: [MTA data]( http://web.mta.info/developers/turnstile.html)
  - The most recent 3 months period: 2021/03 to 2021/05 


##### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
The individual unit of analysis would be each row of data/record as below: 

C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS                                                               
A002,R051,02-00-00,59 ST,NQR456W,BMT,05/08/2021,00:00:00,REGULAR,0007568196,0002585862                                            
A002,R051,02-00-00,59 ST,NQR456W,BMT,05/08/2021,04:00:00,REGULAR,0007568207,0002585868                                            
A002,R051,02-00-00,59 ST,NQR456W,BMT,05/08/2021,08:00:00,REGULAR,0007568213,0002585880                                            
A002,R051,02-00-00,59 ST,NQR456W,BMT,05/08/2021,12:00:00,REGULAR,0007568245,0002585920       


The features I would be working with are as follows:
* EXITS: 
    * The cumulative exit register value for a device
    * Number of people who had exited the station in that single line of record
* TIME:
    * Represents the time (hh:mm:ss) for a scheduled audit event
    * Between each record, there was 4 hours that elapsed
* DATE:
    * Represents the date (MM-DD-YY)
* STATION
    * Represents the station name the device is located at


**Data columns  (total 11 columns):** 
  Index |  Column |   Dtype 
-|---------- | ----------
 0 |  CA      |  object
 1  | UNIT    |object
 2  | SCP    |object
 3  | STATION |  object
 4  | LINENAME | object
 5  | DIVISION | object
 6  | DATE      |object
 7   |TIME  |    object
 8  | DESC    |  object
 9  | ENTRIES  | int64 
 10  |EXITS     |int64 


##### If modeling, what will you predict as your target?
The target of the modeling will be a ranking of the time period at stations that had the highest foot traffic. 
(For example, number 1 might be 4-8pm at 59th ST on weekdays.)


## Tools:
##### 	How do you intend to meet the tools requirement of the project?
- insert online raw data into SQL on Terminal
    * create database (sqlite3 mta.db)
    * add table (CREAT TABLE commands)
    * insert file to table (.mode.csv .import mta_data.csv mta_data)
- querying data into python
    * *```
         from sqlalchemy import create_engine
            ```
    * use commands as CREATE TABLE, GROUP BY to make the simpler tables with certain features columns via SQLite on Jupyter Notebook
- pandas 
    * *```
        	import pandas as pd
            ```
    * data cleaning: remove missing data if any
    * use aggregate function to subtract the number difference of Exits
    
- visual tool
    * *```
        	import matplotlib.pyplot as plt
           ```
    * *```
        	 import seaborn as sns
            ```
    * *```
        	 %matplotlib inline
            ```

##### 	Are you planning in advance to need or use additional tools beyond those required?
I intend to try to use other visualization tools such as pivot table.


## MVP Goal:

##### 	What would a minimum viable product (MVP) look like for this project?
✨A ranking of the time period at stations that had the highest foot traffic. ✨





