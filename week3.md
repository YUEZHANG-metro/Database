
#week 3
## question 1
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
![q1](https://github.com/user-attachments/assets/218016e3-237c-44dc-8cd4-7959a50e4d1e)


## question 2
SELECT name,type 
FROM airport 
WHERE iso_country = 'FI';
<img width="493" alt="q2" src="https://github.com/user-attachments/assets/c42bed1f-580f-40e0-9a09-777944be3466">

## question 3
SELECT name FROM airport 
WHERE iso_country = 'FI' 
ORDER BY name ASC;
<img width="677" alt="q3" src="https://github.com/user-attachments/assets/cd8bddc5-47f2-4cc9-9216-66108238245a">

## question 4
SELECT name,type 
FROM airport
WHERE iso_country = 'FI'
ORDER BY type ASC, name ASC;
<img width="492" alt="q4" src="https://github.com/user-attachments/assets/0948b97f-5944-4395-b6f9-0eeacef7abf0">

## question 5
SELECT name FROM country
WHERE name LIKE 'F%';
![q5](https://github.com/user-attachments/assets/72b69233-9ebb-4c5a-b3fc-ac2afc066f62)

## question 6
SELECT name FROM country 
WHERE name LIKE '%f%' or 'F%';
![q6](https://github.com/user-attachments/assets/3e9abe1b-c73b-4ddd-a181-9fc441487482)

## question 7
SELECT location FROM game WHERE screen_name = 'Vesa';
![q7](https://github.com/user-attachments/assets/19ce13c9-cb46-45d5-af3d-6a22d6bad21a)

## question 8 
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';
![q8](https://github.com/user-attachments/assets/96dff0c0-0b64-48ad-8835-f597795e9c5e)

## question 9
SELECT co2_budget FROM game LIMIT 1;
![q9](https://github.com/user-attachments/assets/a103cd88-2797-48f4-ba79-60cafe9b7a2d)

## question 10
SELECT TRIM(screen_name) AS screen_name, co2_budget, co2_consumed, (co2_budget - co2_consumed) AS co2_left 
FROM game 
WHERE TRIM(screen_name) = 'Ilkka';
![q10](https://github.com/user-attachments/assets/3e9bc748-736c-4ecd-86cc-11eef62f81dc)

## Exercise 3 
## question 1
SELECT country.name AS 'country name', airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country and country.name = 'Iceland';
![q1](https://github.com/user-attachments/assets/99f2016e-983e-4a37-b0ee-780e49194d1d)

## question2
SELECT airport.name AS 'airport name' 
FROM airport, country 
WHERE airport.iso_country = country.iso_country 
AND country.name = 'France' 
AND airport.type = 'large_airport';
![q2 where](https://github.com/user-attachments/assets/821e47a1-9509-4e6b-9807-ace1117c40df)


SELECT airport.name AS 'airport name' 
FROM airport 
JOIN country 
WHERE airport.iso_country = country.iso_country 
and country.name = 'France' 
and airport.type = 'large_airport';
![q2](https://github.com/user-attachments/assets/1237de2b-da24-493b-ba43-b9b8ece86a3f)

## question 3
SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport, country
WHERE airport.iso_country = country.iso_country
AND airport.continent = 'an';
![q3 where](https://github.com/user-attachments/assets/371c6cb2-dced-41b1-b779-1c054bcc3c14)


SELECT country.name AS 'country_name', airport.name AS 'airport_name'
FROM airport
JOIN country
ON airport.iso_country = country.iso_country 
and airport.contient = 'an';
![q3](https://github.com/user-attachments/assets/0af13523-71c9-4463-8357-9c45e9f49948)

## question 4
SELECT airport.elevation_ft
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
![q4 where](https://github.com/user-attachments/assets/72c7dae2-e657-4f1b-a799-b6deac919c02)

SELECT airport.elevation_ft
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
![q4](https://github.com/user-attachments/assets/c4b3d86d-1731-4608-ac5e-b624f4a483fe)

## question 5
SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Heini';
![q5 where](https://github.com/user-attachments/assets/3cdebc45-5221-47e0-8c1a-9c5865ae91b4)


SELECT airport.elevation_ft * 0.3048 AS elevation_m
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Heini';
![q5](https://github.com/user-attachments/assets/7efde413-e2a8-4d55-98d5-daa742d08aa3)

## question 6
SELECT airport.name
FROM airport, game
WHERE game.location = airport.ident
AND game.screen_name = 'Ilkka';
![q6 where](https://github.com/user-attachments/assets/9fc578ab-51c0-4833-bab4-55cc99cde895)

SELECT airport.name
FROM airport
JOIN game
On game.location = airport.ident
WHERE game.screen_name = 'Ilkka';
![q6](https://github.com/user-attachments/assets/6b75b03f-cc9b-431a-b1d8-c7bcbaf15467)

## question 7
SELECT country.name
FROM airport, game, country
WHERE game.location = airport.ident
AND airport.iso_country = country.iso_country
AND game.screen_name = 'Ilkka';
![q7 where](https://github.com/user-attachments/assets/577d9a71-50ba-43b4-b8a3-5073a36f00f4)


SELECT country.name
FROM airport
JOIN game
ON game.location = airport.ident
JOIN country
ON airport.iso_country = country.iso_country 
WHERE game.screen_name = 'Ilkka';
![q7](https://github.com/user-attachments/assets/9e792467-4ca8-4807-b46a-f45eb270b751)


## question 8
SELECT goal.name
FROM goal, goal_reached, game
WHERE goal.id = goal_reached.goal_id
AND game.id = goal_reached.game_id
AND game.screen_name = 'Heini';
![q8 where](https://github.com/user-attachments/assets/a12e973e-268d-4193-a50b-c3084d225f62)

SELECT goal.name 
FROM goal 
JOIN goal_reached 
ON goal.id = goal_reached.goal_id 
JOIN game 
ON game.id = goal_reached.game_id 
WHERE game.screen_name = 'Heini';
![q8](https://github.com/user-attachments/assets/ac3bb3e8-f481-4a1d-99c1-d911b534e253)

## question 9
SELECT airport.name
FROM airport, game, goal_reached, goal
WHERE game.location = airport.ident
AND game.id = goal_reached.game_id
AND goal.id = goal_reached.goal_id
AND game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
![q9 where](https://github.com/user-attachments/assets/d9fe88c1-3e08-499b-905a-d8e2ce2f21d3)

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
![q9](https://github.com/user-attachments/assets/6b661815-8caf-4283-aa80-17b74fd1d96d)



## question 10
SELECT country.name
FROM country, airport, game, goal_reached, goal
WHERE airport.iso_country = country.iso_country
AND game.location = airport.ident
AND game.id = goal_reached.game_id
AND goal.id = goal_reached.goal_id
AND game.screen_name = 'Ilkka'
AND goal.name = 'clouds';
![q10 where](https://github.com/user-attachments/assets/406df64a-10fd-480b-8cb1-31790140d8a6)


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
![q10](https://github.com/user-attachments/assets/153b9d0c-140d-48c6-a167-27bfa3a45c3e)


#week 4

## question 1
'''
SELECT country.name AS 'country name', airport.name AS 'airport name'
FROM airport
JOIN country
ON airport.iso_country = country.iso_country
WHERE country.name = 'Finland'
AND airport.scheduled_service = 'yes';
'''

![q1](./Users/yue/Desktop/Database/week4/q1.png)

