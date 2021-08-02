# HackerRank SQL

### Weather Observation Station 5

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The STATION table is described as follows:

<img src="https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg" alt="Station Table">

where LAT_N is the northern latitude and LONG_W is the western longitude.

<b>Sample Input</b>

For example, CITY has four entries: DEF, ABC, PQRS and WXY.

<b>Sample Output</b>

ABC 3
PQRS 4

<b>Explanation</b>

When ordered alphabetically, the <b>CITY</b> names are listed as <b>ABC, DEF, PQRS, and WXY,</b> with lengths 3, 3, 4 and 3. The longest name is <b>PQRS,</b> but there are 3 options for shortest named city. Choose <b>ABC,</b> because it comes first alphabetically.

<b>Note</b><br>
You can write two separate queries to get the desired output. It need not be a single query.


## Solution
```sql
SELECT CITY, LENGTH(CITY) FROM STATION
WHERE LENGTH(CITY) =                  
(                                     
SELECT MIN(LENGTH(CITY)) FROM STATION 
)                                     
ORDER BY CITY                         
LIMIT 1;                              
                                      
SELECT CITY, LENGTH(CITY) FROM STATION
WHERE LENGTH(CITY) =                  
(                                     
SELECT MAX(LENGTH(CITY)) FROM STATION 
)                                     
ORDER BY CITY                         
LIMIT 1;                              
```
