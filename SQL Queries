# MurderMystery

-- find the report for the crime scene
SELECT *
FROM crime_scene_report
WHERE date = 20180115 and city = "SQL City";
/* security footage shows there were 2 witnesses
    witness 1: lives at the last house on "Northwestern Dr"
    witness 2: named Annabel & lives on "Franklin Ave" */

-- find what information is contained in table 'person'
SELECT *
FROM person;

-- find witness 1
SELECT *
FROM person
WHERE address_street_name = "Northwestern Dr"
ORDER BY address_number DESC;

-- find witness 2
SELECT *
FROM person
WHERE name LIKE "%Annabel%";

-- what info is in table 'facebook_event_checkin"
SELECT *
FROM facebook_event_checkin;

--what events did Annabel attend? 
SELECT *
FROM facebook_event_checkin;
WHERE person_id = 16371;
-- Annabel attended "The Funky Grooves Tour" on the day of the crime

--what events did Morty attend?
SELECT *
FROM facebook_event_checkin
WHERE person_id = 14887;
-- Morty also attended "The Funky Grooves Tour" on the day of the crime

--who else attended "The Funky Groove Tour" on the day of the crime?
SELECT *
FROM facebook_event_checkin
WHERE event_name = "The Funky Grooves Tour";
-- one other person attended 

-- who was the third attendee?
SELECT *
FROM person
WHERE id = 67318;
-- Jeremy Bowers also attended "The Funky Grooves Tour"

-- what did Morty, Annabel & Jeremy tell police? 
SELECT name, id, transcript
FROM interview
JOIN person
  ON person.id = interview.person_id
WHERE person_id = 16371
  OR person_id = 14887
  OR person_id = 67318;

--Annabell's interview: when was Annabell at the gym on 20180109?
SELECT *
FROM get_fit_now_member
JOIN get_fit_now_check_in
  ON get_fit_now_member.id = get_fit_now_check_in.membership_id
 WHERE check_in_date = 20180109
   AND name LIKE "%Annabel%";
   
-- Who else was at the gym between 1600-1700
SELECT *
FROM get_fit_now_member
JOIN get_fit_now_check_in
  ON get_fit_now_member.id = get_fit_now_check_in.membership_id
 WHERE check_in_date = 20180109
   AND check_in_time < 1700
   AND check_out_time > 1600;
 -- Jeremy Bowers & Joe Germuska were at the gym both have member ids statring with "48z"

-- Morty's interview: license plate = "H42W"
SELECT *
FROM drivers_license
JOIN person
  ON drivers_license.id = person.license_id
WHERE plate_number LIKE "%H42W%";

-- Jeremy's interivew: who was the woman that hired him?
SELECT *
FROM drivers_license
JOIN person
  ON drivers_license.id = person.license_id
WHERE gender = "female"
  AND height BETWEEN 65 AND 67
  AND hair_color = "red"
  AND car_make = "Tesla"
  AND car_model = "Model S";

-- which woman attended SQL Symphony Concert?
SELECT *
FROM facebook_event_checkin
WHERE event_name LIKE "%SQL%"
GROUP BY person_id
HAVING person_id = 78881
  OR person_id = 90700
  OR person_id = 99716;

-- confirm name & attendance of person 99716
SELECT *
FROM facebook_event_checkin
JOIN person
  ON facebook_event_checkin.person_id = person.id
WHERE event_name LIKE "%SQL%"
AND person_id = 99716;

-- I mean what if I don't wanna live the way you live? Oh, don't be ridiculous. Andrea. Everybody wants this!
