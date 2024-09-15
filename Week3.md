## week 3 exercise 2

## question 1
Write a query that prints out the name and type of each Finnish airport. Order the result first by type and secondly by name. The output should be as follows:
```
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
```
![q1](week3/q1.png)


## question 2
Write a query that prints out the name and type of each airport in Finland. The country code for Finland is: FI.
```
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
```
![q2](week3/q2.png)

## question 3
Write a query that prints out the names of all Finnish airports in alphabetical order. The country code for Finland is: FI. The output should look as follows (Note that the image has been cropped to fit the screen):
```
SELECT name FROM airport 
WHERE iso_country = 'FI' 
ORDER BY name ASC;
```
![q3](week3/q3.png)

## question 4
Write a query that prints out the name and type of each Finnish airport. Order the result first by type and secondly by name. The output should be as follows:
```
SELECT name,type 
FROM airport
WHERE iso_country = 'FI'
ORDER BY type ASC, name ASC;
```
![q4](week3/q4.png)

## question 5
Write a query that prints out the names of all countries that start with the letter F from the country table. The output should look as follows:
```
SELECT name FROM country
WHERE name LIKE 'F%';
```
![q5](week3/q5.png)

## question 6
Write a query that prints out all country names in the country table that include the letter F. The output should be as follows:
```
SELECT name FROM country 
WHERE name LIKE '%f%' or 'F%';
```
![q6](week3/q6.png)

## question 7
What is Vesa's current location? The output should be as follows:
```
SELECT location 
FROM game 
WHERE screen_name = 'Vesa';
```
![q7](week3/q7.png)

## question 8 
How much of his CO2 budget has Ilkka consumed? The output should look as follows:
```
SELECT co2_consumed FROM game 
WHERE screen_name = 'Ilkka';
```
![q8](week3/q8.png)

## question 9
What is the original CO2 budget? Print out the CO2 budget value only once. The output should be as follows:
```
SELECT co2_budget 
FROM game LIMIT 1;
```
![q9](week3/q9.png)

## question 10
How much of his CO2 budget does Ilkka have left? Complete the query so that the result includes the following fields: screen_name, co2_budget, co2_consumed and co2_left.
```
SELECT TRIM(screen_name) 
AS screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) AS co2_left 
FROM game 
WHERE TRIM(screen_name) = 'Ilkka';
```
![q10](week3/q10.png)

## Exercise 3 
## question 1
Write a query that lists the names of all countries and airports. Select Iceland as the country and assign the following aliases:

name column of the country table:  alias "country name"
name column of the airport table: alias "airport name"
```
SELECT country.name AS 'country name', airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country and country.name = 'Iceland';
```
![q1](week3/weeke3/q1.png)

## question2
Write a query  to list the names of all large airports in France. Assign the name column the alias "airport name".
```
SELECT airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country 
AND country.name = 'France' 
AND airport.type = 'large_airport';
```
![q2where](week3/weeke3/q2where.png)

```
SELECT airport.name AS 'airport name' 
FROM airport 
JOIN country 
WHERE airport.iso_country = country.iso_country 
and country.name = 'France' 
and airport.type = 'large_airport';
```
![q2](week3/weeke3/q2.png)

## question 3
Write a query that lists the names and country names of all airports on Antartica. Use aliases country_name and airport_name. SQLite does not support aliases with multiple words. MariaDB does, but requires the name to be enclosed in quotation marks.
Hint: Continent = "an"
```
SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport, country
WHERE airport.iso_country = country.iso_country
AND airport.continent = 'an';
```
![q3where](week3/weeke3/q3where.png)

```
SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport
JOIN country
ON airport.iso_country = country.iso_country 
and airport.contient = 'an';
```
![q3](week3/weeke3/q3.png)

## question 4
What is the height of Heini's current location measured from the sea level?
```
SELECT airport.elevation_ft
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
```
![q4where](week3/weeke3/q4where.png)

```
SELECT airport.elevation_ft
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
```
![q4](week3/weeke3/q4.png)

## question 5
What is the height of Heini's current location measured from the sea level? Print out the result in meters and assign the result the alias elevation_m. One feet corresponds to 0.3048 meters.
```
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
```
![q5where](week3/weeke3/q5where.png)

```
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
```
![q5](week3/weeke3/q5.png)

## question 6
What is the name of the airport Ilkka is currently at?
```
SELECT airport.name
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Ilkka';
```
![q6where](week3/weeke3/q6where.png)

```
SELECT airport.name
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Ilkka';
```
![q6](week3/weeke3/q6.png)

## question 7
What is the name of the country Ilkka is currently at?
```
SELECT country.name
FROM airport, game, country
WHERE game.location = airport.ident
AND airport.iso_country = country.iso_country
AND game.screen_name = 'Ilkka';
```
![q7where](week3/weeke3/q7where.png)

```
SELECT country.name
FROM airport
JOIN game
ON game.location = airport.ident
JOIN country
ON airport.iso_country = country.iso_country 
WHERE game.screen_name = 'Ilkka';
```
![q7](week3/weeke3/q7.png)


## question 8
List the weather condition goals Heini as achieved so far.
```
SELECT goal.name
FROM goal, goal_reached, game
WHERE goal.id = goal_reached.goal_id
AND game.id = goal_reached.game_id
AND game.screen_name = 'Heini';
```
![q8where](week3/weeke3/q8where.png)

```
SELECT goal.name 
FROM goal 
JOIN goal_reached 
ON goal.id = goal_reached.goal_id 
JOIN game 
ON game.id = goal_reached.game_id 
WHERE game.screen_name = 'Heini';
```
![q8](week3/weeke3/q8.png)

## question 9
Print out the name of the airport where Ilkka achieved the clouds weather goal. 
```
SELECT airport.name
FROM airport, game, goal_reached, goal
WHERE game.location = airport.ident
AND game.id = goal_reached.game_id
AND goal.id = goal_reached.goal_id
AND game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
```
![q9where](week3/weeke3/q9where.png)

```
SELECT airport.name
FROM airport
JOIN game
ON game.location = airport.ident
JOIN goal_reached
ON game.id = goal_reached.game_id 
JOIN goal
ON goal.id = goal_reached.goal_id 
WHERE game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
```
![q9](week3/weeke3/q9.png)


## question 10
Print out the name of the country where Ilkka achieved the clouds goal.
```
SELECT country.name
FROM country, airport, game, goal_reached, goal
WHERE airport.iso_country = country.iso_country
AND game.location = airport.ident
AND game.id = goal_reached.game_id
AND goal.id = goal_reached.goal_id
AND game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
```
![q10where](week3/weeke3/q10where.png)

```
SELECT country.name
FROM country
JOIN airport
ON airport.iso_country = country.iso_country
JOIN game
ON game.location = airport.ident
JOIN goal_reached
ON game.id = goal_reached.game_id 
JOIN goal
ON goal.id = goal_reached.goal_id 
WHERE game.screen_name = 'Ilkka' and goal.name = 'clouds';
```
![q10](week3/weeke3/q10.png)
