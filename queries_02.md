
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
GROUP BY `exam_id`
```

# 4 Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT COUNT(`id`) AS `courses`, `degree_id`
FROM `courses`
GROUP BY `degree_id`
```

## Join:
# 5 Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
SELECT students.degree_id , students.name , degrees.name
FROM students
INNER JOIN degrees ON degrees.id = students.degree_id
```

# 6 Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql

```

# 7 Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql

```

# 8 Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql

```

# 9 Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql

```

# 10 Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
```sql

```

# BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami
```sql

```