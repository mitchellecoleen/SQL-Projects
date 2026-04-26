# SQL-Projects
# Hospital_Data_
#1. Show first name, last name, and gender of patients whose gender is 'M'
SELECT 
    first_name,
    last_name,
    gender
FROM patients
WHERE gender = 'M'

#2. Show first name and last name of patients who does not have allergies. (null)
SELECT 
    first_name,
    last_name
FROM patients
Where allergies IS NULL;

#3. Show first name of patients that start with the letter 'C'
SELECT 
	first_name
FROM patients
Where first_name like 'C%'

#4. Show first name and last name of patients that weight within the range of 100 to 120 (inclusive)
SELECT 
	first_name,
    last_name
FROM patients
Where WEIGHT between 100 AND 120

#5. Update the patients table for the allergies column. If the patient's allergies is null then replace it with 'NKA'
UPDATE patients
SET allergies = 'NKA'
WHERE allergies IS NULL;

#6. Show first name and last name concatinated into one column to show their full name.
SELECT CONCAT(first_name,' ',last_name) AS full_name
FROM patients;

#7. Show first name, last name, and the full province name of each patient.
SELECT 
	first_name,
    last_name,
    province_name
FROM patients
 JOIN province_names ON patients.province_id = province_names.province_id
 
 # Fetch all of the people who are either unemployed or between the ages of 20 and 28 (including 20 and 28) but not age 22.
 SELECT *
FROM people
WHERE status = 'unemployed'


OR (age BETWEEN 20 AND 28 AND age <>22);

#Fetch all of the colorful objects. Instead of writing colorful = 1 try to use the TRUE keyword.
SELECT *
FROM objects
WHERE id IS NOT FALSE AND colorful IS TRUE;

#Fetch all of the unique names without missing values.
SELECT *
FROM people
WHERE name IS NOT NULL;

#As an owner of a vehicle factory, you have agreed to provide a salary raise for the four employees with the lowest salaries who are also married, as they are struggling to finance their families. Return only the IDs of the relevant employees. Sort the results by salary in ascending order.
