# SECTION 07 HW 


# 7.1 HW Questions 

## 1. Using EVregistry, Write a query to select the `ModelYear`, `Make`, and `Model` off all of the vehicles in the registry.
```SQL

--SELECT ModelYear, Make, Model
--FROM EVRegistry

```
## 2. Using the EVRegistry table, Write a query that lists all of the unique types of EV's. your reult set should have one column, `ElectricVehicleType`. 
```SQL

-- SELECT DISTINCT ElectricVehicleType
-- FROM EVRegistry 

```
## 3. Using the EVRegistry, Write a query that shows all of the information on Battery Electric Vehicles (BEV) that are in the registry. 
```SQL

-- select *
-- from EVRegistry
-- where ElectricVehicleType = 'Battery Electric Vehicle (BEV)'

```
## 4. Using the EVRegistry, wirte a query that returns the `Make` and `Model` of all of the EV's that have a BaseMSRP between 20000 and 35000?  
```SQL

-- SELECT Make, Model
-- FROM EVRegistry
-- where BaseMSRP BETWEEN 20000 and 35000

```


# 7.2 HW Questions 

## 1. Using EVRegistry, write a query to find a record  where the `City` attribute is NULL. Return all of the available columns. 
```SQL

-- SELECT *
-- from EVRegistry
-- where City is NULL

```
## 2. Write a query to find the `make`, `model`, and `ElectricVehicleType` where the VIN number has  that ends in '3E1EA1J'.
```SQL

-- SELECT Make, Model, ElectricVehicleType, VIN
-- from EVRegistry
-- where VIN like '%3E1EA1J'

```
## 3. Select the `ModelYear`, `make`, `model`, `ElectricVehicleType`, and `range` of the Tesla vehicles or cheverolet vehicles in the registry. Order the result set by Make and Model year in from newest to oldest. 
```SQL

-- SELECT ModelYear, Make, Model, ElectricVehicleType, ElectricRange
-- from EVRegistry
-- where Make = 'TESLA' or make = 'CHEVROLET'
-- ORDER by 1 DESC, 2

```
## 4. Using EVCharging, Write a query to find out how many many times those stations were used. Order them by the most used to the least used and limit the output to 5 records. 
```SQL

-- SELECT stationId, 
-- 	count(userId) as stationUsage
-- from EVCharging
-- group by 1
-- order by 2 DESC
-- limit 5

```
## 5.  Using EVCharging, For the folks who charged longer than 0.5 hours, show the min and max of the charging time for each user. Your output columns should be `userid`, `minTime`, and `maxTime`. Order this result set by the last two columns respectively. 
```SQL

-- SELECT userId,
-- 	min(chargeTimeHrs)as minTime,
-- 	max(chargeTimeHrs)as maxTime
-- from EVCharging
-- where chargeTimeHrs > 0.5
-- group by 1
-- order by 2, 3

```


# 7.3 HW Questions

## 1. Using EVCharging, Which day of the week has the highest average charging time? Round the answer to 2 decimal points.
```SQL

-- SELECT weekday,
-- 	round(avg(chargetimehrs), 2) as timeAvg
-- from EVCharging
-- group by 1
-- ORDER by 2 DESC

-- Wednesday

```
## 2. Using, EV charging, Find the total power consumed from charging EV's by each User. Return the `userId` and name the calculated column, `totalPower`. Round the answer to 2 deciaml points and list the out put in highest to lowest order. Limit the order to the top 15 users. 
```SQL

-- select userId,
-- 	round(sum(kwhTotal), 2) as totalPower
-- from EVCharging
-- GROUP by 1
-- ORDER by 2 DESC
-- limit 15

```
## 3. Using dimfacility and factCharge, write a query to find out which type of facility (GROUP BY) has the most amount of charging stations. Return `type Facility` and name the calculated column `numStation`. Order the result set from highest to lowest number of charging stations.  
```SQL

-- SELECT dimFacility.typeFacility, 
-- 	count(DISTINCT stationid) as numStation
-- from dimFacility
-- JOIN factCharge
-- on dimFacility.FacilityKey =factCharge.facilityID
-- group by 1
-- order by 2 DESC

-- Research and Development

```
## 4. In your own words, Briefly explain Primary Keys and Foreign Keys. 
```SQL

--A Primary key identifies the records in a table while the foreign key helps connect another table with similar record identifiers.

```
##5. Using EV Charging, For the folks who charged longer than one hour, show the min and max of the charging time for each user. Your output columns should be `userid`, `minTime`, and `maxTime`. Order this result set by the last two columns respectively. HINT: USE `HAVING`
```SQL

-- SELECT userId,
-- 	min(chargeTimeHrs)as minTime,
-- 	max(chargeTimeHrs)as maxTime
-- from EVCharging
-- group by 1
-- HAVING chargeTimeHrs > 1
-- order by 2, 3

```


