## week 3 exercise 2

## question 1
```
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
```
![q1](week3/q1.png)


## question 2
```
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
```
![q2](week3/q2.png)

## question 3
```
SELECT name FROM airport 
WHERE iso_country = 'FI' 
ORDER BY name ASC;
```
![q3](week3/q3.png)

## question 4
```
SELECT name,type 
FROM airport
WHERE iso_country = 'FI'
ORDER BY type ASC, name ASC;
```
![q4](week3/q4.png)

## question 5
```
SELECT name FROM country
WHERE name LIKE 'F%';
```
![q5](week3/q5.png)

## question 6
```
SELECT name FROM country 
WHERE name LIKE '%f%' or 'F%';
```
![q6](week3/q6.png)

## question 7
```
SELECT location 
FROM game 
WHERE screen_name = 'Vesa';
```
![q7](week3/q7.png)

## question 8 
```
SELECT co2_consumed FROM game 
WHERE screen_name = 'Ilkka';
```
![q8](week3/q8.png)

## question 9
```
SELECT co2_budget 
FROM game LIMIT 1;
```
![q9](week3/q9.png)

## question 10
```
SELECT TRIM(screen_name) 
AS screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) AS co2_left 
FROM game 
WHERE TRIM(screen_name) = 'Ilkka';
```
![q10](week3/q10.png)

## Exercise 3 
## question 1
```
SELECT country.name AS 'country name', airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country and country.name = 'Iceland';
```
![q1](week3/week e3/q1.png)

## question2
```
SELECT airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country 
AND country.name = 'France' 
AND airport.type = 'large_airport';
```
![q2where](week3/week e3/q2 where.png)

```
SELECT airport.name AS 'airport name' 
FROM airport 
JOIN country 
WHERE airport.iso_country = country.iso_country 
and country.name = 'France' 
and airport.type = 'large_airport';
```
![q2](week3/week e3/q2.png)

## question 3
```
SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport, country
WHERE airport.iso_country = country.iso_country
AND airport.continent = 'an';
```
![q3 where](https://github.com/user-attachments/assets/371c6cb2-dced-41b1-b779-1c054bcc3c14)

```
SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport
JOIN country
ON airport.iso_country = country.iso_country 
and airport.contient = 'an';
```
![q3](week3/week e3/q3.png)

## question 4
```
SELECT airport.elevation_ft
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
```
![q4 where](https://github.com/user-attachments/assets/72c7dae2-e657-4f1b-a799-b6deac919c02)

```
SELECT airport.elevation_ft
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
```
![q4](week3/week e3/q4.png)

## question 5
```
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
```
![q5 where](https://github.com/user-attachments/assets/3cdebc45-5221-47e0-8c1a-9c5865ae91b4)

```
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
```
![q5](week3/week e3/q5.png)

## question 6
```
SELECT airport.name
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Ilkka';
```
![q6 where](https://github.com/user-attachments/assets/9fc578ab-51c0-4833-bab4-55cc99cde895)

```
SELECT airport.name
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Ilkka';
```
![q6](week3/week e3/q6.png)

## question 7
```
SELECT country.name
FROM airport, game, country
WHERE game.location = airport.ident
AND airport.iso_country = country.iso_country
AND game.screen_name = 'Ilkka';
```
![q7 where](https://github.com/user-attachments/assets/577d9a71-50ba-43b4-b8a3-5073a36f00f4)

```
SELECT country.name
FROM airport
JOIN game
ON game.location = airport.ident
JOIN country
ON airport.iso_country = country.iso_country 
WHERE game.screen_name = 'Ilkka';
```
![q7](week3/week e3/q7.png)


## question 8
```
SELECT goal.name
FROM goal, goal_reached, game
WHERE goal.id = goal_reached.goal_id
AND game.id = goal_reached.game_id
AND game.screen_name = 'Heini';
```
![q8 where](https://github.com/user-attachments/assets/a12e973e-268d-4193-a50b-c3084d225f62)

```
SELECT goal.name 
FROM goal 
JOIN goal_reached 
ON goal.id = goal_reached.goal_id 
JOIN game 
ON game.id = goal_reached.game_id 
WHERE game.screen_name = 'Heini';
```
![q8](week3/week e3/q8.png)

## question 9
```
SELECT airport.name
FROM airport, game, goal_reached, goal
WHERE game.location = airport.ident
AND game.id = goal_reached.game_id
AND goal.id = goal_reached.goal_id
AND game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
```
![q9 where](https://github.com/user-attachments/assets/d9fe88c1-3e08-499b-905a-d8e2ce2f21d3)

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
![q9](week3/week e3/q9.png)


## question 10
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
![q10 where](https://github.com/user-attachments/assets/406df64a-10fd-480b-8cb1-31790140d8a6)

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
![q10](week3/week e3/q10.png)
