# Основные запросы SELECT

1. ### Вывести идентификаторы курсов (предметов).
```python
SELECT courseid
FROM course;
```
2. ### Вывести всю информацию о курсах (предметах).
```python
SELECT * 
FROM course;
```
3. ### Вывести идентификатор курса с названием "Machine Learning".
```python
SELECT courseid
FROM course
WHERE coursetitle = 'Machine Learning';
```
4. ### Вывести название курса с идентификатором 5.
```python
SELECT coursetitle
FROM course
WHERE courseid = 5;
```
5. ### Вывести список мобильных телефонов из таблицы "PHONE_LIST".
```python
SELECT phone
FROM phone_list
WHERE phonetype = 'cell';
```
6. ### Вывести количество отметок, которое получил студент с идентификатором (номером зачетки) 345576.
```python
SELECT count(grade)
FROM exam_result
WHERE studentid = 345576;
```
7. ### Вывести номера зачеток (идентификаторы студентов) и средние баллы, которые получили студенты за все экзамены.
```python
SELECT studentid, AVG(grade) 
FROM exam_result 
GROUP BY studentid;
```
8. ### Вывести минимальный и максимальный баллы, полученные студентами на экзаменах.
```python
SELECT MAX(grade), MIN(grade) 
FROM exam_result;
```
9. ### Найти пересечение идентификаторов студентов, получавших и 2, и 5. Каждый идентификатор из пересечения должен встречаться не более одного раза.
```python
SELECT studentid FROM exam_result WHERE grade = 2
INTERSECT
SELECT studentid FROM exam_result WHERE grade = 5;
```
10. ### Найти объединение идентификаторов студентов, у которых есть хоть одна двойка и/или хоть одна пятерка. Каждый идентификатор из пересечения должен встречаться не более одного раза.
```python
SELECT studentid FROM exam_result WHERE grade = 2
UNION 
SELECT studentid FROM exam_result WHERE grade = 5;
```
