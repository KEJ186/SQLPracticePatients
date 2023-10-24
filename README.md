# SQLPracticePatients - https://www.sql-practice.com/

SELECT * FROM patients
COLUMNS: patient_id, first_name, last_name, gender, 
birth_date, city, province_id, allergies, height, weight,
/*
  Start by selecting a question by pressing 'Start' or 'View All Questions'.
  Use the resources and information about the database from the left panel to help.
  Press the run button to execute the query.
  Question is automatically validated every time you execute the query.
  Make your output match the expected output.
 
 
  Keybinds:
    [ctrl + enter]: Execute the SQL
    [ctrl + q]: Auto-format the SQL
*/
*******************************************************************
Show first name and last name of patients 
that weight within the range of 100 to 120 (inclusive)

SELECT first_name,last_name
FROM patients
WHERE weight BETWEEN 100 and 120;
**************************************************************************
Update the patients table for the allergies column. 
If the patient's allergies is null then replace it with 'NKA'

UPDATE patients
SET allergies = 'NKA'
WHERE allergies IS NULL;
********************************************************************
Show first name and last name concatinated
into one column to show their full name.

SELECT
  CONCAT(first_name, ' ', last_name) AS full_name
FROM patients;
*********************************************************************

Show first name, last name, and the full province name of each patient.
Example: 'Ontario' instead of 'ON'

SELECT
  first_name,
  last_name,
  province_name
FROM patients
  JOIN province_names ON province_names.province_id = patients.province_id;

SELECT *
FROM province_names
*********************************************************************
Show how many patients have a birth_date with 2010 as the birth year.

COLUMNS: patient_id, first_name, last_name, gender, 
birth_date, city, province_id, allergies, height, weight,

SELECT COUNT (*)
FROM patients
WHERE YEAR(birth_date)=2010

SELECT COUNT(*) AS total_patients
FROM patients
WHERE YEAR(birth_date) = 2010;
*************************************************************************






