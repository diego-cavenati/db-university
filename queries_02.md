
## Group by:
# 1 Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT COUNT(`id`) as `total_student`, YEAR(`enrolment_date`) as `year`
FROM `students`
GROUP BY `year`;
```

# 2 Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT COUNT(`id`) AS `teachers_number`, `office_address`
FROM `teachers`
GROUP BY `office_address`;
```

# 3 Calcolare la media dei voti di ogni appello d'esame
```sql
SELECT `exam_id`, AVG(`vote`) AS `grade_point_average`
FROM `exam_student`
GROUP BY `exam_id`;
```

# 4 Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT COUNT(`id`) AS `courses`, `degree_id`
FROM `courses`
GROUP BY `degree_id`;
```

## Join:
# 5 Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
SELECT `students`.*
FROM `students`
JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

# 6 Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql
SELECT `degrees`.* 
FROM `degrees` 
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Neuroscienze' AND `degrees`.`level` = 'magistrale';
```

# 7 Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql
SELECT `courses`.* 
FROM `courses` 
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id` 
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id` 
WHERE `teachers`.`id` = 44;
```

# 8 Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql
SELECT `students`.`name` AS `name`, `students`.`surname` AS `surname`, `students`.`id` AS `id`, `degrees`.`name` AS `degrees`, `departments`.`name` AS `departments`
FROM `students` 
JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id` 
ORDER BY `students`.`surname` , `students`.`name` ASC;
```

# 9 Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql
SELECT `degrees`.`name`, `courses`.`name`, `teachers`.`surname`
FROM `courses` 
JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id` 
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id` 
ORDER BY `Corso di Laurea`
```

# 10 Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```sql
SELECT `teachers`.* 
FROM `teachers` 
JOIN `course_teacher` ON `course_teacher`.`teacher_id` = `teachers`.`id` 
JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id`  
JOIN `degrees` ON  `degrees`.`id` = `courses`.`degree_id` 
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica' 
ORDER BY `teachers`.`id`
```

# BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami
```sql

```