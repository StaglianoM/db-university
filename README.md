### 1 Selezionare tutti gli studenti nati nel 1990 ###

```SQL

SELECT * 
FROM `db-university`.students
WHERE date_of_birth LIKE '1990%';
```

### 2 Selezionare tutti i corsi che valgono più di 10 crediti  ###

```SQL
SELECT * 
FROM `db-university`.courses
WHERE cfu > 10;
```

### 3 Selezionare tutti gli studenti che hanno più di 30 annI ###

```SQL
SELECT * 
FROM `db-university`.students
WHERE YEAR(CURDATE()) - YEAR(date_of_birth) > 30;
```

### 4 Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea  ###
```SQL
SELECT * 
FROM `db-university`.courses
WHERE year = 1 AND period = 'I semestre';
```

### 5 Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 ###
```SQL
SELECT * 
FROM `db-university`.exams
WHERE DATE(date) = '2020-06-20' 
  AND TIME(hour) > '14:00:00';
```

### 6 Selezionare tutti i corsi di laurea magistrale ###
```SQL
SELECT * 
FROM `db-university`.degrees
WHERE level LIKE 'magistrale'
```