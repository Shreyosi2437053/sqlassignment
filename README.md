--STEP 1
SELECT *
FROM crime_scene_report
WHERE type = 'murder'
AND city = 'SQL City'
AND date = 20180115

<img width="406" alt="image" src="https://github.com/user-attachments/assets/4a23dd0f-dd18-4612-91a6-aad363733764">

--STEP 2
SELECT *
FROM person
WHERE address_street_name = 'Northwestern Dr'
ORDER BY address_number DESC
LIMIT 1

<img width="395" alt="image" src="https://github.com/user-attachments/assets/da03b8b0-2e9e-4a11-9611-96d93a4f2961">

--STEP 3
SELECT *
FROM person
WHERE address_street_name = 'Franklin Ave'
LIMIT 10

<img width="415" alt="image" src="https://github.com/user-attachments/assets/00f58971-9e45-4661-a73a-226a88ec3464">

--STEP 4
SELECT *
FROM person
WHERE address_street_name = 'Franklin Ave'
AND name LIKE '%Annabel%'
LIMIT 10

<img width="411" alt="image" src="https://github.com/user-attachments/assets/c8293f2d-a11a-4d7b-af04-2f21188643dc">

--STEP 5
SELECT *
FROM interview
WHERE person_id IN (14887,16371) 
LIMIT 10

<img width="425" alt="image" src="https://github.com/user-attachments/assets/b092767d-0840-4723-b46e-2472dca8f819">

--STEP 6
SELECT *
FROM drivers_license
WHERE plate_number LIKE '%H42W%'
LIMIT 10

<img width="420" alt="image" src="https://github.com/user-attachments/assets/adba1b0c-d182-45a8-9a0d-330896d56b71">

--STEP 7
SELECT p. *
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

<img width="421" alt="image" src="https://github.com/user-attachments/assets/88a9e568-6765-4f3b-8ddc-29fd3fefbcf6">

--STEP 8
SELECT p. *
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

<img width="440" alt="image" src="https://github.com/user-attachments/assets/64814f64-ddf7-49b9-9bde-1267354c6330">

--STEP 9
SELECT p. * , gf.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
LEFT JOIN get_fit_now_member as gf on p.id = gf.person_id
WHERE plate_number LIKE '%H42W%'
LIMIT 10

<img width="425" alt="image" src="https://github.com/user-attachments/assets/9b8f5153-cfc6-4f87-8e47-6059df15ef1b">

--STEP 10
SELECT p. * , ci.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
INNER JOIN get_fit_now_check_in as ci on gf.id = ci.membership_id
WHERE plate_number LIKE '%H42W%'
AND membership_status = 'gold'
LIMIT 10

<img width="422" alt="image" src="https://github.com/user-attachments/assets/e9cf0930-bb71-46fd-8df6-883c7d283f33">

--STEP 11
SELECT p. * , ci.*
FROM drivers_license as d1
INNER JOIN person as p on d1.id = p.license_id
INNER JOIN get_fit_now_member as gf on p.id = gf.person_id
INNER JOIN get_fit_now_check_in as ci on gf.id = ci.membership_id
WHERE plate_number LIKE '%H42W%'
AND membership_status = 'gold'
AND check_in_date = 20180109
LIMIT 10

<img width="424" alt="image" src="https://github.com/user-attachments/assets/8e7289cf-848e-4070-abad-7aa349c6fa41">

--STEP 12

<img width="440" alt="image" src="https://github.com/user-attachments/assets/c7863c5d-0575-45fd-baa0-68d532c3ac11">

--STEP 13
SELECT p.*, fb.*
FROM drivers_license as dl
INNER JOIN person as p on dl.id = p.license_id
INNER JOIN facebook_event_checkin as fb on fb.person_id = p.id
WHERE hair_color = 'red'
AND height >= 65
AND height <= 67
AND car_make = 'Tesla'
And car_model = 'Model S'
AND gender = 'female'
LIMIT 100

<img width="419" alt="image" src="https://github.com/user-attachments/assets/cfe26274-95ca-4cf5-99ae-e7af9edd732f">

--STEP 14

<img width="442" alt="image" src="https://github.com/user-attachments/assets/3bd6d7bf-7f1f-4a9f-afca-a09951c2040c">

"# sqlassignment" 
