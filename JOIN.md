### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia ###

```SQL
SELECT `s`.*
FROM `students` AS `s`
JOIN `degrees` AS `d` ON `s`.`degree_id` = `d`.`id`
WHERE `d`.`name` LIKE '%Economia%';
```


### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze ###

```SQL
SELECT `d`.*
FROM `degrees` AS `d`
JOIN `departments` AS `dep` ON `d`.`department_id` = `dep`.`id`
WHERE `d`.`name` LIKE '%Magistrale%' AND `dep`.`name` LIKE '%Neuroscienze%';


```


### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL
SELECT c.*
FROM `courses` AS `c`
JOIN `course_teacher` AS `ct` ON c.id = ct.course_id
JOIN `teachers` AS `t` ON ct.teacher_id = t.id
WHERE t.name = 'Fulvio' AND t.surname = 'Amato';

```


### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome ###

```SQL
SELECT 
    `s`.*, `d`.`name` AS `degree_name`, `dep`.`name` AS `department_name`
FROM 
    `students` AS `s`
JOIN 
    `degrees` AS `d` ON `s`.`degree_id` = `d`.`id`
JOIN 
    `departments` AS `dep` ON `d`.`department_id` = `dep`.`id`
ORDER BY 
    `s`.`surname` ASC, `s`.`name` ASC;
```


### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti ###

```SQL
SELECT 
    `d`.`name` AS `degree_name`,
    `c`.`name` AS `course_name`,
    `t`.`name` AS `teacher_name`,
    `t`.`surname` AS `teacher_surname`
FROM 
    `degrees` AS `d`
JOIN 
    `courses` AS `c` ON `d`.`id` = `c`.`degree_id`
JOIN 
    `course_teacher` AS `ct` ON `c`.`id` = `ct`.`course_id`
JOIN 
    `teachers` AS `t` ON `ct`.`teacher_id` = `t`.`id`;
```


### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) ###
```SQL
SELECT DISTINCT `t`.*
FROM `departments` AS `dep`
JOIN `degrees` AS `d`
ON `dep`.`id` = `d`.`department_id`
JOIN `courses` AS `c`
ON `c`.`degree_id` = `d`.`id`
JOIN `course_teacher` AS `c_t`
ON `c_t`.`course_id` = `c`.`id`
JOIN `teachers` AS `t`
ON `c_t`.`teacher_id` = `t`.`id`
WHERE `dep`.`name` = 'Dipartimento di Matematica'
```


### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18 ###

```SQL
SELECT `s`.`name`,`s`.`surname`,`s`.`id` AS `student_id`,
`c`.`id` AS `course_id`, COUNT(*) AS `tentativi`,
MAX(`e_s`.`vote`) AS `voto_massimo`
FROM `students` AS `s`
JOIN `exam_student` AS `e_s`
ON `e_s`.`student_id` = `s`.`id`
JOIN `exams` AS `e`
ON `e_s`.`exam_id` = `e`.`id`
JOIN `courses` AS `c`
ON `e`.`course_id` = `c`.`id`
GROUP BY `s`.`id`, `c`.`id`
HAVING `voto_massimo` >= 18
```