# Patient-Data
Here i showed data information. For example: names, what province they were at and if the had any allergies. I also looked for specific patients, for example by weight and height.

1.Show first name, last name, and gender of patients who's gender is 'M'
/*
SELECT first_name, last_name, gender 
FROM patients
WHERE gender = 'M';
*/

2.Show first name and last name of patients who does not have allergies. (null)
/*
SELECT first_name, last_name 
FROM patients 
WHERE allergies IS NULL
*/

3.Show first name of patients that start with the letter 'C'
/*
select first_name 
FROM patients 
WHERE first_name LIKE 'C%'
*/

4. Show first name and last name of patients that weight within the range of 100 to 120 (inclusive)
/*
select first_name, last_name
FROM patients
WHERe weight 
between 100 and 120
*/

5.Update the patients table for the allergies column. If the patient's allergies is null then replace it with 'NKA'
/*
update patients
SET allergies = 'NKA' 
WHERE allergies IS NULL
*/

6.
Show first name and last name concatinated into one column to show their full name.
/*
select CONCAT (first_name, ' ', last_name) AS full_name
FROM patients
*/

7.Show first name, last name, and the full province name of each patient.
/*
select first_name, last_name, province_name
FROM patients 
JOIN provinces 
ON provinces.province_id = patients.province_id
*/

8.Show how many patients have a birth_date with 2010 as the birth year.
/*
SELECT COUNT (birth_date)
FROM patients 
WHERE Year (birth_date) =2010
*/

9.Show the first_name, last_name, and height of the patient with the greatest height.
/*
select first_name, last_name, MAX (height) 
FROM patients
*/

10.Show all columns for patients who have one of the following patient_ids: 1,45,534,879,1000
/*
SELECT * 
FROM patients 
WHERE patient_id IN (1,45,534,879,1000)
*/

11.Show the total number of admissions
/*
select count(admission_date) 
FROM admissions
*/

12.Show all the columns from admissions where the patient was admitted and discharged on the same day.
/*
select * From admissions
where (admission_date = discharge_date)
*/

13.Show the total number of admissions for patient_id 573.
/*
select patient_id, count(*) AS total_admissions 
from admissions 
where patient_id = 573
*/

14.Based on the cities that our patients live in, show unique cities that are in province_id 'NS'?
/*
select DISTINCT city
FROm patients
WHERE province_id IS 'NS'
*/

15.Write a query to find the first_name, last name and birth date of patients who have height more than 160 and weight more than 70
/*
select first_name, last_name, birth_date 
From patients 
WHERE (height >160 and weight >70)
*/

16.Write a query to find list of patients first_name, last_name, and allergies from Hamilton where allergies are not nka or null
/*
select first_name, last_name, allergies 
FROM patients 
WHERE city is 'Hamilton' 
ANd allergies is NOT 'NKA'
AND allergies IS NOT NULL
*/
