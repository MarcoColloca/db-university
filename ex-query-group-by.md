# EX - Query con GROUP BY
---
1. Contare quanti iscritti ci sono stati ogni anno

        SELECT COUNT(`students`.`id`) 
        
        AS `number_of_students`, `enrolment_date`

        FROM `students`        

        GROUP BY `enrolment_date`;
---
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio


---
3. Calcolare la media dei voti di ogni appello d'esame

        SELECT COUNT(`exams`.`id` ), `date`, AVG(`exam_student`.`vote`) AS `average_students_vote`

        FROM `exams`

        INNER JOIN `exam_student`

        ON `exam_student`.`exam_id` = `exams`.`id`

        GROUP BY `date`;

---
4. Contare quanti corsi di laurea ci sono per ogni dipartimento

        SELECT COUNT(`degrees`.`name`) AS `number_of_degrees`, `departments`.`name` AS `department_name`

        FROM `departments`

        INNER JOIN `degrees`

        ON `departments`.`id` = `degrees`.`department_id`

        GROUP BY `departments`.`name`;

---