### Selezionare tutti gli studenti nati nel 1990 ###

```SQL

SELECT * 
FROM `db-university`.students
WHERE date_of_birth LIKE '1990%';
```

### Selezionare tutti i corsi che valgono più di 10 crediti  ###

```SQL
SELECT * 
FROM `db-university`.courses
WHERE cfu > 10;
```

### Selezionare tutti gli studenti che hanno più di 30 annI ###

```SQL
SELECT * 
FROM `db-university`.students
WHERE YEAR(CURDATE()) - YEAR(date_of_birth) > 30;
```

### Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea  ###
```SQL


```