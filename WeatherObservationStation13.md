# HackerRank SQL

### Weather Observation Station 13

Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.2345. Truncate your answer to 4 decimal places.

**Input Format**

The STATION table is described as follows:

![Station Table](https://s3.amazonaws.com/hr-challenge-images/9336/1449345840-5f0a551030-Station.jpg)

where LAT_N is the northern latitude and LONG_W is the western longitude.

## Solution
```sql
SELECT ROUND(SUM(LAT_N),4) FROM STATION
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```