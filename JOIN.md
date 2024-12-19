### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia ###
```SQL
SELECT s.*
FROM students s
JOIN degrees d ON s.degree_id = d.id
WHERE d.name LIKE '%Economia%';
```


### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze ###
```SQL
SELECT d.*
FROM degrees d
JOIN departments dep ON d.department_id = dep.id
WHERE d.name LIKE '%Magistrale%' AND dep.name LIKE '%Neuroscienze%';

```


### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```SQL

```


### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome ###
```SQL

```


### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti ###
```SQL

```


### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) ###
```SQL

```


### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18 ###

```SQL

```