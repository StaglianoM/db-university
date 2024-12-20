### 1 Selezionare tutti gli studenti nati nel 1990 ###

```SQL

SELECT * 
FROM students
WHERE date_of_birth LIKE '1990%';
```

### 2 Selezionare tutti i corsi che valgono più di 10 crediti  ###

```SQL
SELECT * 
FROM courses
WHERE cfu > 10;
```

### 3 Selezionare tutti gli studenti che hanno più di 30 annI ###

```SQL
SELECT * 
FROM students
WHERE YEAR(CURDATE()) - YEAR(date_of_birth) > 30;
```

### 4 Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea  ###
```SQL
SELECT * 
FROM courses
WHERE year = 1 AND period = 'I semestre';
```

### 5 Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 ###
```SQL
SELECT * 
FROM exams
WHERE DATE(date) = '2020-06-20' 
  AND TIME(hour) > '14:00:00';
```

### 6 Selezionare tutti i corsi di laurea magistrale ###
```SQL
SELECT * 
FROM degrees
WHERE level LIKE 'magistrale'
```

### 7 Da quanti dipartimenti è composta l'università? ###
```SQL
SELECT COUNT(*) AS name_departments
FROM departments;
```

### 8 Quanti sono gli insegnanti che non hanno un numero di telefono? ###
```SQL
SELECT COUNT(*) AS teachers_no_phone
FROM teachers
WHERE phone IS NULL;
```

### 9 Inserire nella tabella degli studenti un nuovo record con i propri dati  ###
```SQL
INSERT INTO students (name, surname, date_of_birth, degree_id, fiscal_code, enrolment_date, registration_number, email)
VALUES ('Pippo', 'Tivoli', '1992-01-01', 1, 'ABCDE123456', '2024-01-01', '123456', 'pippo.a.tivoli@boolean.com');
```

### 10 Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126 ###
```SQL
UPDATE `techers`
SET `office_number` = '126'
WHERE `id` = 
```

### 11 Eliminare dalla tabella studenti il record creato precedentemente al punto ###
```SQL
DELETE FROM students
WHERE id = XXXX;
```
<!-- DELETE FROM students
WHERE name = 'Pippo' AND surname = 'Tivoli' AND date_of_birth = '1992-01-01'; -->