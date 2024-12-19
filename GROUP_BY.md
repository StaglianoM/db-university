### 1. Contare quanti iscritti ci sono stati ogni anno ### 
```SQL
SELECT YEAR(enrolment_date) AS year, COUNT(*) AS total_students
FROM students
GROUP BY YEAR(enrolment_date)
ORDER BY enrolment_year;
```

###  2. Contare gli insegnanti che hanno l'ufficio nello stesso  edificio ### 
```SQL
SELECT office_number, COUNT(*) AS total_teachers
FROM teachers
GROUP BY office_number;
```
###  3. Calcolare la media dei voti di ogni appello d'esame ### 
```SQL
SELECT student_id, AVG(vote) AS average_vote
FROM exam_student
GROUP BY student_id;
```
###  4. Contare quanti corsi di laurea ci sono per ogni dipartimento  ### 
```SQL
SELECT department_id, COUNT(*) AS total_degrees
FROM degrees
GROUP BY department_id;
```
