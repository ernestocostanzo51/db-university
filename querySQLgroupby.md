1. Contare quanti iscritti ci sono stati ogni anno
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
3. Calcolare la media dei voti di ogni appello d'esame
4. Contare quanti corsi di laurea ci sono per ogni dipartimento


1. SELECT YEAR(enrolment_date) AS anno, COUNT(ID) AS totale
FROM students
GROUP BY year(enrolment_date)
ORDER BY year(enrolment_date) ASC

2. SELECT office_address as indirizzo, COUNT(ID) as numero_uffici
FROM teachers
GROUP BY office_address
ORDER BY indirizzo

3. SELECT exam_id , ROUND(AVG(vote), 0) AS media_voti
FROM exam_student 
GROUP BY exam_id

4. SELECT department_id, COUNT(ID)
FROM degrees
GROUP BY department_id