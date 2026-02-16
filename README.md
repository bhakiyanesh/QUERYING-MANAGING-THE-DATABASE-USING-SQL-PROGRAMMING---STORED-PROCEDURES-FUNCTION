# QUERYING-MANAGING-THE-DATABASE-USING-SQL-PROGRAMMING---STORED-PROCEDURES-FUNCTION
AIM: 
To query and manage the database using SQL Programming for Stored PROCEDUREs and Functions. 
BUILT-IN FUNCTIONS 
1. AGGREGATE FUNCTIONS 
(a) AVG - To find the average of values. 
Example: Find the average of account balance from the account table 
Query: select avg (balance) from account; 
(b) SUM – To find the sum of values. 
Example: Find the sum of account balance from the account table 
Query: select sum (balance) from account; 
(c) MAX – Returns the maximum value. 
Example: Find the Maximum value of account balance from the account table. 
Query: select max (balance) from account; 
(d) MIN - Returns the minimum value. 
Example: Find the Minimum value of account balance from the account table. 
Query: select min (balance) from account; 
(e) COUNT – Returns the number of rows in the column or table. 
Example 1: Find the number rows in the customer table. 
Query: select count (*) from customer; 
Example 2: Find the number of rows in the balance column of account table. 
Query: select count (balance) from account; 
(f) GROUP BY 
Example 1: Find the average account balance at each branch. 
Query:select branch_name, avg (balance) from account group by branch_name; 
Example 2: Find the average account balance at brighton branch. 
Query:  select  branch_name,  avg  (balance)  from account  group by branch_name  having 
branch_name=’brighton’; 
 
  
 
 
2. NUMERIC FUNCTIONS: 
i) ABS-Returns the absolute value. 
Example: select abs (-19) from dual; 
ii) CEIL- Returns the smallest integer value greater than number 
Example: select ceil (40.678) from dual; 
iii) FLOOR – Returns the largest integer value less than the number 
Example: select floor (40.678) from dual; 
iv) POWER (n1, n2) – Returns the n1 to the power n2 
Example: select power (4, 6) from dual; 
v) ROUND (n1, n2) – Returns n1 after rounding n1 with respect to n2 decimal places. 
Example: select round (66666.8888, 2) from dual; 
vi) TRUNC (n1, n2)- Returns n1 after truncating n1 with respect to n2 decimal places. 
Example: select trunc (66666.8888, 2) from dual; 
vii) EXP- Returns the exponentiation of the given number. 
Example: select exp (5) from dual; 
viii) SQRT – Returns the square root of the given number. 
Example: select sqrt (36) from dual; 
 
3. CHARACTER FUNCTIONS: 
i) CHR (number)- Returns the character equivalent of the ASCII number 
Example: select chr (75) from dual; 
ii) LENGTH (String) – Returns the number of character in the string 
Example: select cust_name, length (cust_name) from customer where cust_city='rye' 
iii) LOWER (String) – returns the lower case letters 
Example: select lower (‘CAPE INSTITUTE OF TECHNOLOGY’) from dual; 
iv) UPPER (String) – returns the upper case letters 
Example: select upper (branch_name) from branch; 
v) INITCAP- returns the first character is Upper 
Example: select initcap (branch_name) from branch; 
vi) SUBSTR (String, n1, n2)- returns the substring of the string starting from n1 position to n2 
number of characters 
Example: select substr (‘computerscience’, 9,7) from dual; 
 
  
 
 
4. DATE FUNCTIONS: 
i) ADD_MONTHS (Date, number) returns the date after adding number of months with the given 
date 
Example: select add_months (’01-sep-01’, 3) from dual; 
ii) MONTHS_BETWEEN (date1, date2) returns the number of months in between date1 and 
date2 
Example: select months_between ('01-may-02','01-feb-02’) from dual; 
iii) LAST_DAY (date) –returns the last date of that month. 
Example Example: select last_day (’12-jun-98’) from dual; 
iv) SYSDATE – returns the system date 
Example: select sysdate from dual; 
v) NEXT_DAY (d, day)– returns the date of the next day. 
Example: select next_day (sysdate,’monday’) from dual; 
 
5. CONVERSION FUNCTIONS: 
i) TO_DATE (charStringdate, dateFormat) converts the charstringdate to the date. It will accept 
the charStringdate according to the date format specified. 
Example: select to_date (’january 02 1999’, ‘month-dd-yyyy’) from dual; 
select to_date('02 february 2000','dd-month-yyyy')from dual; 
ii) TO_CHAR (date, format) returns the character equivalent of the date according to the format. 
Example: select to_char (sysdate, ‘ddth” of “ fmmonth yyyy’) from dual; 
Example: select to_char (to_date (’january 02 1999’, ‘month-dd-yyyy’), ‘ddth” of “ fmmonth 
yyyy’) from dual; 
iii) TO_CHAR (n [, fmt]) returns a value of number data type to a value of char data type 
Example: select to_char (17145,’$099,999’) from dual; 
iv) TO_NUMBER (charNumeric) returns the number equivalent of the charNumeric 
Example: select to_number (‘123’) from dual; 
 
STORED PROCEDURES 
DESCRIPTION: 
SYNTAX: 
CREATE [OR REPLACE] PROCEDURE name [(parameter[,parameter,…])] 
{IS|AS} 
[local declarations] 
 
  
 
 
BEGIN 
executable statements 
[EXCEPTION 
exception handlers] 
END [name]; 
PROCEDURE FOR GCD NUMBERS 
create or replace PROCEDURE 
PROCEDURE1 is 
 
 
 
 
 
 
begin 
a number(3); 
b number(3); 
c number(3); 
d number(3); 
 
 
a:=&a; 
b:=&b; 
if(a>b) then 
c:=mod(a,b); 
if(c=0) then 
dbms_output.put_line('GCD is'); 
dbms_output.put_line(b); 
else 
dbms_output.put_line('GCD is'); 
dbms_output.put_line(c); 
end if; 
else 
d:=mod(b,a); 
if(d=0) then 
dbms_output.put_line('GCD is'); 
dbms_output.put_line(a); 
else 
dbms_output.put_line('GCD is'); 
dbms_output.put_line(d); 
end if; 
end if; 
end; 
 
  
 
 
/ 
FUNCTIONS 
SYNTAX: 
CREATE [OR REPLACE] FUNCTION name 
[(parameter[,parameter, ...])] 
RETURN datatype 
{IS | AS} 
[local declarations] 
BEGIN 
executable statements 
RETURN value; 
[EXCEPTION 
exception handlers] 
END [name]; 
To write a PL/SQL block to find factorial of given number using function. 
Filename: fact.sql 
create or replace function fact(limit number) return number is 
ans number(3); 
I number(3); 
begin 
 
 
 
 
 
 
 
 
end; 
/ 
 
 
ans:=1; 
for i in 1..limit loop 
ans:=ans*i; 
end loop; 
return(ans); 
 
 
Filename: test.sql 
declare 
 
 
 
begin 
n number(3); 
f number(3); 
 
n:=&limit; 
f:=fact(n); 
 
  
 
 
dbms_output.put_line(n||'! = '||f); 
end; 
/ 
OUTPUT: 
SQL> fact.sql 
Function Created. 
SQL> test.sql 
Enter value for Limit: 4 
old 5: n:=&limit; 
new 5: n:=4; 
4! = 24 
PL/SQL PROCEDURE successfully completed. 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
RESULT: 
Thus, querying and managing the database using SQL Programming for Stored PROCEDUREs 
and Functions has been successfully completed.
