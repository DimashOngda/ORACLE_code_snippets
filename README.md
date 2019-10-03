# ORACLE_code_snippets
This is the just some snippets of oracle sql dev.


SELECT field.field_id, station.station_name as station_name FROM station  
INNER JOIN FIELD ON
station.station_id = field.station_id
WHERE Extract(YEAR FROM FIELD.YEAR_OF_AMMOUNT) = 2004 AND ROWNUM = 1
ORDER BY FIELD.ANNUAL_PROD; 
--||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||
SELECT field.field_id,station.station_name as station_name FROM FIELD
INNER JOIN MINERALS ON
FIELD.minerals_id = minerals.minerals_id
INNER JOIN STATION ON
field.station_id=station.station_id
WHERE (UNIT_PRICE*0.1) < FIELD.extraction_cost;
--||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||
SELECT station.station_name as station_name , Annual_prod FROM FIELD
INNER JOIN STATION ON
field.station_id = station.station_id
WHERE STATION_NAME = 'Bestobe'
ORDER BY annual_prod DESC;
--||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||
SELECT station_name FROM Station  
INNER JOIN FIELD ON  field.station_id = station.station_id
GROUP BY station_name
HAVING SUM(Annual_prod)  > 100000 and COUNT(MINERALS_ID) > 3;  

