
drop table attandance;
drop table tutorial;
drop table course ;
drop table niveau;
drop table student;
drop table teacher;

drop table lang;

drop table payment;
-- tables
CREATE TABLE attandance (
    id_attandance integer  PRIMARY KEY,
    student_id_student integer  ,
    tutorial_id_tutorial integer  ,
    payment_id_payment integer,
    FOREIGN KEY (student_id_student) REFERENCES student (id_student),
    FOREIGN KEY (tutorial_id_tutorial) REFERENCES TUTORIAL (ID_TUTORIAL)
    
) ;

-- Table: course
CREATE TABLE course (
    id_course integer PRIMARY KEY ,
    lesson integer  ,
    desc_of varchar2(200)  ,
    lang_id_lang integer  ,
    niveau_id_niveau integer ,
    price integer ,
    FOREIGN KEY( niveau_id_niveau)  REFERENCES niveau(id_niveau),
    FOREIGN KEY (lang_id_lang) REFERENCES lang(id_lang)
) ;

-- Table: lang
CREATE TABLE lang (
    id_lang integer  PRIMARY KEY,
    sign varchar2(5)  ,
    name_of varchar2(20)  
) ;

-- Table: niveau
CREATE TABLE niveau (
    id_niveau integer  PRIMARY KEY,
    name varchar2(50)  
   
) ;

-- Table: payment
CREATE TABLE payment (
    id_payment integer  PRIMARY KEY,
    payment_date date ,
    amount integer , 
    id_attandance integer,
    FOREIGN KEY (id_attandance) REFERENCES attandance(id_attandance)
) ;

-- Table: student
CREATE TABLE student (
    id_student integer  PRIMARY KEY,
    name varchar2(20)  ,
    surname varchar2(20)  ,
    date_of_birth date  ,
    phone integer  

) ;

-- Table: teacher
CREATE TABLE teacher (
    id_Teacher integer PRIMARY KEY,
    first_name varchar2(20)  ,
    last_name varchar2(20) ,
    phone integer 
) ;



-- Table: tutorial
CREATE TABLE tutorial (
    id_tutorial integer  PRIMARY KEY,
    name varchar2(20)  ,
    start_date date  ,
    end_date date  ,
    teacher_id_Teacher integer  ,
    course_id_course integer ,
    FOREIGN KEY( teacher_id_Teacher)  REFERENCES teacher(id_teacher),
    FOREIGN KEY (course_id_course) REFERENCES course(id_course)
 
) ;
select* from course;



 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (1,'GOKCE','ALTUNKANAT','05464350999','27-SEP-2000');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (2,'SEVVAL','BAZ','05337583924','15-APR-2000');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (3,'BEYZA','AKTAS','05855612933','10-MAY-2000');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (5,'MELISA','AKKAYA','05670283461','03-FEB-2000');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (6,'NURDAN','EKE','05438594229', '22-MAY-1969');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (7,'ERDEM','ALTUNKANAT','05444609199', '30-JUN-1974');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (8,'JACK','HARWOOD','05336694641','13-JUL-2006');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (9,'AZRA','ELA','05336963200', '13-JUN-2003');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (10,'BATU','EKE','05498984549', '28-MAR-1999');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (202,'Ismail','PINARBASI','03498984549', '24-MAR-1998');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (203,'YILMAZ','EKE','05498984500', '22-AUG-1997');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (204,'BATU','EKER','05498984009', '18-SEP-1997');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (205,'EMRE','ALDI','05498900549', '01-JUL-1993');
 
 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (206,'FIKRET','DEMIR','05490084549', '17-APR-1994');



INSERT INTO TEACHER(ID_TEACHER , first_name, last_name, phone)
VALUES(11,'GOKHAN','OZER','05557467832');

INSERT INTO TEACHER(ID_TEACHER , first_name, last_name, phone)
VALUES(12,'BECKY','BELLIS','05626354771');

INSERT INTO TEACHER(ID_TEACHER , first_name, last_name, phone)
VALUES(13,'TINA','SMITH','05856473732');

INSERT INTO TEACHER(ID_TEACHER , first_name, last_name, phone)
VALUES(14,'AARON','MILLER','05557467832');

INSERT INTO TEACHER(ID_TEACHER , first_name, last_name, phone)
VALUES(15,'AYSEL','MARTINEZ','05448181832');




INSERT INTO lang(id_lang,sign,name_of)
values (44,'A1','elementary');

INSERT INTO lang(id_lang,sign,name_of)
values (45,'A2','pre-intermadiate');

INSERT INTO lang(id_lang,sign,name_of)
values (46,'B1','low-intermadiate');

INSERT INTO lang(id_lang,sign,name_of)
values (47,'B2','intermadiate');

INSERT INTO lang(id_lang,sign,name_of)
values (48,'C1','advance');



INSERT INTO niveau(ID_NIVEAU,name)
values (51,'english');

INSERT INTO niveau(ID_NIVEAU,name)
values (52,'german');


INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(53,1,'Learning the basics of german language ',44,52,'2500');

INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(54,1,'Learning the beginning of english language ',45,51,'3500');

INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(55,1,'Learning the pre-intermadiate of german language ',46,52,'4000');

INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(56,1,'Learning the intermadiate of german language ',47,52,'3800');

INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(57,1,'Learning the advance features in english language ',48,51,'2750');

INSERT INTO course (id_course,lesson,desc_of,lang_id_lang,niveau_id_niveau,price)
values(58,1,'Learning the basics of english language ',44,51,'3000');




INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(131,11,53,'Elementary German','01-JAN-2021','01-MAR-2021');

INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(132,12,58,'Elementary English','01-JAN-2021','01-MAR-2021');

INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(133,13,54,'Pre-Inter English','01/03/2021','01/06/2021');

INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(134,14,55,'Low-Inter German','15-JAN-2021','15-MAR-2021');

INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(135,15,56,'Intermadiate German','15-JAN-2021','15-MAR-2021');

INSERT INTO tutorial (id_tutorial,teacher_id_teacher,course_id_course,name,start_date,end_date)
values(136,11,57,'Advance English','01-FEB-2021','01-APR-2021');



INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(75,1,131);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(76,2,132);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL,payment_id_payment)
VALUES(77,3,133);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(78,5,134);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(79,6,135);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(80,7,136);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(81,8,133);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(82,9,134);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(83,10,135);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(84,202,131);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(85,203,132);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(86,204,136);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(87,205,132);

INSERT INTO ATTANDANCE(ID_ATTANDANCE,STUDENT_ID_STUDENT,TUTORIAL_ID_TUTORIAL)
VALUES(88,206,134);


select* from attandance ;



INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1000,'20-DEC-2020',2500,75);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1001,'20-FEB-2021',3500,76);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1002,'10-JAN-2021',3500,77);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1003,'21-DEC-2020',4000,78);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1004,'01-FEB-2021',3800,79);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1005,'11-FEB-2021',2750,80);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1006,'28-NOV-2021',3500,81);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1009,'03-DEC-2020',4000,82);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1008,'09-DEC-2020',3800,83);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1009,'01-FEB-2021',2500,84);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1010,'15-JAN-2021',3000,85);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1011,'03-JAN-2021',2750,86);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1012,'22-DEC-2020',3000,87);

INSERT INTO PAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT,ID_ATTANDANCE)
VALUES(1013,'14-DEC-2020',4000,88);


SELECT* FROM STUDENT ;
select* from  teacher;
select* from attandance;
select*from tutorial;
select*from course;
select* from payment;
select*from niveau;
select*from lang;

--QUERIES

--1--find tutorials which has more than 2 student
select tutorial_id_tutorial from attandance 
group by tutorial_id_tutorial
having count (student_id_stuDENT)>2;

--2--DISPLAY THE PAYMENTS MADE BY STUDENT 'ERDEM ALTUNKANAT'  

SELECT * FROM PAYMENT ,STUDENT ,attandance
WHERE student.id_student=attandance.student_id_student  and  attandance.id_attandance=payment.attandance_id_attandance and 
 NAME = 'ERDEM' AND SURNAME ='ALTUNKANAT';

--3--find students who payed between  '1-dec-20' AND '31-dec-20' by student id

SELECT id_student, name, surname FROM student
WHERE EXISTS (SELECT 1 FROM payment,attandance  WHERE
student.id_student=attandance.student_id_student 
and  attandance.id_attandance=payment.attandance_id_attandance and 
PAYMENT_DATE BETWEEN '1-dec-20' AND '31-dec-20')
order by id_student;
       
--4--VERTICAL JOIN-- find students who are born after 1998

SELECT
id_student 
FROM student 
MINUS 
SELECT id_student
FROM student
where date_of_birth<'01-jan-99';

--5-- Find students who supervised by gokhan ozer
Select name, surname from tutorial, student, attandance
Where student.id_student=attandance.student_id_student and attandance.tutorial_id_tutorial=tutorial.id_tutorial and
teacher_id_teacher = (select id_teacher from teacher
Where first_name like 'GOKHAN' and last_name like 'OZER');

--6-- write when and which tutorial starts and finish with string format

select name ||' class starts on '|| start_date||' and finishes on '||end_date|| 'with id number '||id_tutorial
from tutorial;

--7-- find courses which has prices 3000 and more than 3000
SELECT price,desc_of
FROM   course
WHERE  price >= 3000
order by price;

--8-- find id courses which is english 
select name_of_niveau, id_course
from niveau , course where niveau.id_niveau=course.niveau_id_niveau and name_of_niveau='english';

--9-- find student who payed first 
select name, payment_date
from student ,payment ,attandance
WHERE  student.id_student=attandance.student_id_student  and 
attandance.id_attandance=payment.attandance_id_attandance and payment_DATE = (SELECT MIN(payment_DATE) FROM PAYMENT);
  

--10--find a teachers who is not teaching to any tutorial group
select id_teacher from teacher
where id_teacher not in (select teacher_id_teacher from tutorial );



drop trigger payment_check;
drop trigger max_price;
drop trigger teacher_count;
drop trigger tutorial_view;
drop trigger not_allow_changes;
drop trigger prevent_removal;

SELECT* FROM TUTORIAL;
--2022




-- PROCEDURES

--create procedure riseprice which increase course prices between 2000-3000
--WORKS--CURSOR AND EXCEPTION 
CREATE TABLE CCOURSE  AS
SELECT * FROM COURSE;

DROP PROCEDURE RISEPRICE;

SET SERVEROUTPUT ON;
CREATE OR REPLACE PROCEDURE RISEPRICE
AS
NONIVEAUID EXCEPTION;
X NUMBER;
IDP NUMBER;
CURSOR C1 IS
SELECT ID_COURSE
FROM CCOURSE
WHERE PRICE BETWEEN '2000' AND '3000';
BEGIN
SELECT COUNT(ID_COURSE) INTO X
FROM CCOURSE
WHERE PRICE BETWEEN '2000' AND '3000';
IF X = 0 THEN
RAISE NONIVEAUID;
ELSE
OPEN C1;
LOOP
FETCH C1 INTO IDP;
EXIT WHEN C1%NOTFOUND;
UPDATE CCOURSE SET PRICE = PRICE*1.1 WHERE PRICE BETWEEN  '2000' AND '3000' AND  ID_COURSE = IDP;
END LOOP;
CLOSE C1;
END IF;

EXCEPTION
WHEN NONIVEAUID THEN
DBMS_OUTPUT.PUT_LINE('NO LEVEL ID ');
END;

EXECUTE RISEPRICE;
select* from ccourse;



-- 2   -- EXCEPTION AND CURSOR 
-- Create procedure COURSE_STARTS_ON_FEB shows courses starts in feb 
-- PROCEDURES
DROP PROCEDURE COURSE_STARTS_ON_FEB;
set serveroutput on ;

CREATE or replace  procedure COURSE_STARTS_ON_FEB
AS
nofound exception;
Cursor a1 IS
SELECT NAME from tutorial where start_date between '01-FEB-21' and '28-FEB-21' ;
Y  VARCHAR(30);
x VARCHAR2(11);
BEGIN
select COUNT(name) into x from tutorial;
if x=0 then 
raise nofound;
else
    open a1 ;
    loop fetch a1 into y;
        exit when a1%notfound ;
    dbms_output.put_line(y);
    end loop ;
    end if;
    close a1;
    EXCEPTION WHEN NOFOUND THEN DBMS_OUTPUT.PUT_LINE('NO DATA FOUND');

end;

EXEC COURSE_STARTS_ON_FEB ;
DROP PROCEDURE COURSE_STARTS_ON_FEB;
select * from student ;




CREATE TABLE Cpayment  AS
SELECT * FROM payment;
drop procedure disscount;
SET SERVEROUTPUT ON;


--3 create procedure that shows all course description which has price higher than 3000
set serveroutput on ;
DROP PROCEDURE course_data;
CREATE or replace  procedure course_data
AS
a varchar(200);
x integer;
nofound exception;
Cursor b1 IS
SELECT desc_of from course where  price >3000 ;
BEGIN
select count(id_course)into x from course where price>3000; 
if x=0 then raise nofound;
else
    open b1 ;
    loop fetch b1 into  a;
        exit when b1%notfound ;
 dbms_output.Put_line( a);

    end loop ;
    end if ;
    close b1;
     EXCEPTION WHEN NOFOUND THEN DBMS_OUTPUT.PUT_LINE('NO DATA FOUND');
end;
EXEC course_data;
SELECT* FROM PAYMENT;


--TRIGGER  --- CURSOR AND EXCEPTION 
--1 CREATE TRIGGER before INSERT OR UPDATE SHOWS THE MAX PAYMENT 
drop trigger check_max;
set SERVEROUTPUT ON;
CREATE TABLE Ppayment  AS
SELECT * FROM payment;

CREATE OR REPLACE TRIGGER CHECK_MAX
BEFORE INSERT or update  ON Ppayment
for each row
declare
x integer;
amount Ppayment.amount%type;
NOPAYMENT EXCEPTION;
AMOUNT1 INTEGER ;
CURSOR C1 IS 
SELECT AMOUNT FROM PPAYMENT where AMOUNT =(SELECT MAX(AMOUNT)FROM Ppayment);
BEGIN 
SELECT count(AMOUNT) INTO X
FROM PPAYMENT ;
IF X = 0 THEN
RAISE NOPAYMENT;
ELSE
OPEN C1;
loop FETCH C1 INTO amount1;
DBMS_OUTPUT.PUT_LINE(amount1 );
EXIT WHEN C1%NOTFOUND;
end loop;
end if;
close c1 ;
EXCEPTION WHEN NOPAYMENT THEN 
DBMS_OUTPUT.PUT_LINE('PAYMENT HISTORY IS EMPTY');
END;


INSERT INTO PPAYMENT (ID_PAYMENT,PAYMENT_DATE,AMOUNT)
VALUES(10405,to_date('20/02/2021','dd/mm/yyyy'),3500);

drop trigger CHECK_MAX;


-- TRIGGER 2 --EXCEPTION AND CURSOR-- working-- create a trigger shows before insert new years payments and mutliply by 1.5

set serveroutput on;
create or replace trigger a
before insert on upayment
for each row
declare
h DATE;
invalid exception ;
cursor y3 is
select payment_date from upayment ;
begin
open y3;
loop
fetch y3 into h;
EXIT WHEN  y3%notfound ;
if :new.payment_date < '01-JAN-22' then
raise invalid;
else if
:new.payment_date >= '01-JAN-22' then
:new.amount := :new.amount * 1.5;
end if;
end if;
end loop;
close y3;

exception when invalid then
dbms_output.put_line('SBD');
end;

insert into payment (ID_PAYMENT,PAYMENT_DATE,AMOUNT,id_attandance)
VALUES(4053,'01-FEB-22',3800,79);
SELECT* FROM PAYMENT;
DROP TRIGGER A;
select name  ,sysdate from student ;

--- trigger 3 -- before insert student it shows details of student if we inserted with the same name 
set serveroutput on;
drop trigger show_sameName_students;
create or replace trigger show_sameName_students before insert on Student
for each row
Declare
noCount exception;
s_bd date;
s_id int;
s_count number;
cursor cur is
select id_student from Student where name = :new.name;
begin
select COUNT(id_student) into s_count from Student
where name = :new.name;
if s_count = 0 then raise noCount;
else
dbms_output.put_line('There are ' || s_count || ' students with this name');
open cur;
Loop
fetch cur into s_id;
exit when cur%notfound;
Select date_of_birth into s_bd from student
where id_student = s_id;
dbms_output.put_line('Student ID: ' || s_id || ' Name: '||  :new.name || ' Date of Birth: ' || s_bd);
end loop;
close cur;
end if;
exception when noCount then dbms_output.put_line('error');
END;

 INSERT INTO STUDENT (ID_STUDENT, NAME ,SURNAME , PHONE,DATE_OF_BIRTH )
 VALUES (50919,'YILMAZ','EK','05498984500', '22-AUG-1997');

-- procedure which for given number will show all names of students with id smaller than given number 


create or replace procedure give_number( u integer )
as
idnumber integer;
novalue exception;
a2 varchar2(20);
cursor a1  is select name from student where id_student<u;
begin
select count(name) as idnumber from student where id_student<u;
if(idnumber = 0) then
raise novalue;
else 
open a1;
loop fetch a1 into a2;
exit when a1%notfound;
dbms_output.put_line(a2);
end loop;
close a1;
end if;
exception when novalue then
dbms_output.put_line();








