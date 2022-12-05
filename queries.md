# 1 seleziono tutti gli studenti nati nel 1990 (160)
```sql
SELECT * 
FROM `students`
WHERE `date_of_birth` 
LIKE "1990%";
```

# 2 seleziono tutti i corsi che valgono più di 10 crediti (479)
```sql
SELECT * 
FROM `courses`
WHERE `cfu` > 10;
```

# 3 seleziono tutti gli studenti che hanno più di 30 anni
```sql
SELECT * 
FROM `students`
WHERE `date_of_birth` > "1992%";
```

# 4 seleziono tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
```sql
SELECT * 
FROM `courses`
WHERE `period` = "I semestre" AND `year` = "1";
```

# 5 seleziono tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
```sql
SELECT * 
FROM `exams`
WHERE `date` = "2020-06-20" AND `hour` > "13:59:59";
```

# 6 seleziono tutti i corsi di laurea magistrale (38)
```sql
SELECT * 
FROM `degrees`
WHERE `level` = "magistrale";
```

# 7 Trovo di quanti dipartimenti è composta l'università (12)
```sql
SELECT COUNT(id) 
FROM `departments`;
```

# 8 Trovo di quanti sono gli insegnanti che non hanno un numero di telefono (50)
```sql
SELECT COUNT(id) 
FROM `teachers`
WHERE `phone` IS NOT NULL;
```
