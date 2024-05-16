# EX - Query con JOIN

---

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

        SELECT `students`.*, `degrees`.`name` AS `degree_name`

        FROM `students`

        INNER JOIN `degrees`
	        ON `degrees`.`department_id` = `students`.`degree_id`

        WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

---

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

        SELECT `degrees`.*, `departments`.`name` AS `department_name`

        FROM `degrees`

        INNER JOIN `departments`        
	        ON `departments`.`id` = `degrees`.`department_id`

        WHERE `degrees`.`level` = 'magistrale'

        AND `departments`.`name` = 'Dipartimento di Neuroscienze';

---

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

        SELECT `courses`.*, `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`

        FROM `courses`

        INNER JOIN `course_teacher`
            ON `course_teacher`.`course_id` = `courses`.`id`

        INNER JOIN `teachers`
            ON `course_teacher`.`teacher_id` = `teachers`.`id`

        WHERE `teachers`.`id` = 44;

---

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

        SELECT `students`.`surname` AS `student_surname`, `students`.`name` AS `student_name`, `degrees`.*, `departments`.`name` AS `department_name`

        FROM `students`

        INNER JOIN `degrees`
            ON `students`.`degree_id` = `degrees`.`id`

        INNER JOIN `departments`
            ON `departments`.`id` = `degrees`.`department_id`

        ORDER BY `student_surname`, `student_name`;

---

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

        SELECT `degrees`.*, `teachers`.*

        ROM `courses`

        INNER JOIN `course_teacher`
             ON `course_teacher`.`course_id` = `courses`.`id`
        
        INNER JOIN `teachers`
        	ON `course_teacher`.`teacher_id` = `teachers`.`id`
            
        INNER JOIN `degrees`
        	ON `courses`.`degree_id` = `degrees`.`id`;

---

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

---

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

---