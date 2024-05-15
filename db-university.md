# Consegna
### Nota: le parole che hanno un leggero sfondo grigio (`esempio`), sono inserite tra backtick. 
<br>
<br>
<br>

1. Selezionare tutti gli studenti nati nel 1990 (160): <br>

    SELECT * <br>
    FROM `students` <br>
    WHERE YEAR("`date_of_birth`) = 1990; 
    <br><br>

2. Selezionare tutti i corsi che valgono più di 10 crediti (479) <br>
    SELECT * <br>
    FROM `courses` <br>
    WHERE `cfu` > 10; <br>
    <br><br>


3. Selezionare tutti gli studenti che hanno più di 30 anni <br>
    SELECT * , CURDATE() AS `date_now`, TIMESTAMPDIFF(YEAR,`date_of_birth`,CURDATE()) AS age <br>
    FROM `students` <br>
    WHERE TIMESTAMPDIFF(YEAR,`date_of_birth`,CURDATE()) > 30; <br>
    <br><br>

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso  di laurea (286) <br>
    SELECT *  <br>
    FROM `courses` <br>
    WHERE `period` = 'I semestre' <br>
    AND `year` = 1; <br>
    <br><br>

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14)  del 20/06/2020 (21) <br>
    SELECT *  <br>
    FROM `exams` <br>
    WHERE `date` = '2020-06-20' <br>
    AND TIME_FORMAT(`hour`, '%H:%i') > '14:00'; <br>
    <br><br>


6. Selezionare tutti i corsi di laurea magistrale (38) <br>
SELECT *  <br>
FROM `degrees` <br>
WHERE `level` = 'magistrale'; <br>
<br><br>

7. Da quanti dipartimenti è composta l'università? (12) <br>
SELECT COUNT(*) AS `number_of_departments` <br>
FROM `departments`; <br>
<br><br>

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50) <br>