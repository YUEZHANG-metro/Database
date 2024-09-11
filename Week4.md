#week 4

## question 1
```
SELECT country.name AS 'country name', airport.name AS 'airport name'
FROM airport
JOIN country
ON airport.iso_country = country.iso_country
WHERE country.name = 'Finland'
AND airport.scheduled_service = 'yes';
```
![q1](week4/q1.png)

## question 2
```
SELECT game.screen_name, airport.name
FROM game
LEFT JOIN airport
ON game.location = airport.ident;
```
![q2](week4/q2.png)

## question 3

```
SELECT game.screen_name, country.name
FROM game
LEFT JOIN airport
ON game.location = airport.ident
JOIN country
ON airport.iso_country = country.iso_country;
```
![q3](week4/q3.png)


## question 4
```
SELECT airport.name, game.screen_name
FROM airport
LEFT JOIN game
ON game.location = airport.ident
WHERE airport.name like '%Hels%';
```
![q4](week4/q4.png)

## question 5
```
SELECT goal.name,game.screen_name
FROM goal
LEFT JOIN goal_reached
ON goal.id = goal_reached.goal_id
LEFT JOIN game
ON goal_reached.game_id = game.id;
```
![q5](week4/q5.png)


## WEEK4 exercise5
## question 1
```
SELECT country.name FROM country
WHERE country.iso_country IN (
    SELECT airport.iso_country
    FROM airport
    WHERE airport.name like '%Satsuma%'
    );
```
![q1e5](week4/q1e5.png)

## question2
```
SELECT airport.name FROM airport
WHERE airport.iso_country IN (
    SELECT country.iso_country
    FROM country
    WHERE country.name = 'Monaco'
    );
```
![q2e5](week4/q2e5.png)

## question 3
```
SELECT game.screen_name 
FROM game
WHERE game.id IN  (
    SELECT goal_reached.game_id 
    FROM goal_reached
    WHERE goal_reached.goal_id IN (
        SELECT goal.id 
        FROM goal
        WHERE goal.name = 'Clouds'
        )
);
```
![q3e5](week4/q3e5.png)

## question 4
```
SELECT country.name 
FROM country
WHERE country.iso_country NOT IN(
    SELECT airport.iso_country 
    FROM airport
);
```
![q4e5](week4/q4e5.png)

## question 5
```
SELECT goal.name 
FROM goal
WHERE goal.id NOT IN(
    SELECT goal_reached.goal_id 
    FROM goal_reached
    WHERE goal_reached.game_id IN(
        SELECT game.id 
        FROM game
        WHERE game.screen_name = 'Heini'
    )
);
```
![q5e5](week4/q5e5.png)