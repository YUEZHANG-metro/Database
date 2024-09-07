
#week 3
## question 1
SELECT name,type FROM airport 
WHERE iso_country = 'FI';
![q1](https://github.com/user-attachments/assets/9fef7dff-8950-4002-8a7d-6a439b26a598)

## question 2
SELECT name,type FROM airport 
WHERE iso_country = 'FI';
<img width="493" alt="q2" src="https://github.com/user-attachments/assets/c42bed1f-580f-40e0-9a09-777944be3466">

## question 3
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name ASC;
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







