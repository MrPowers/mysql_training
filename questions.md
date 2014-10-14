1. What is an ERD?

An ERD consists of entities, relationships, and databases.  The "ERDs"
on Tumbler on really schema diagrams and I think we should stop calling
them ERDs.


2. Sub questions are broken out below:

a. Where do we keep our mdc_prod schema diagram?

Tumbler.

b. The table ACCOUNT_PROVIDER was introduced recently, so this question asks you not to use it. Without ACCOUNT_PROVIDER table, how can we get provider for a lab_account? Explain your steps in words in a file. Write a sql statement to get all providers for LAB_ACCT_KEY=20 in a file named 'answer_to_provider_question.sql'. Please don't specify database name in the script so that the grader can test it in appropriate DB.

```sql
select * from LAB_ACCOUNT AS la
INNER JOIN LOCATION AS l ON la.LAB_SRC_KEY = l.LAB_SRC_KEY
INNER JOIN LOCATION_PROVIDER AS lp ON l.LOC_KEY = lp.LOC_KEY
INNER JOIN PROVIDER AS p ON lp.PROV_KEY = p.PROV_KEY
WHERE la.LAB_ACCT_KEY = 20;
```


3. What is JOIN, INNER JOIN, LEFT JOIN, LEFT OUTER JOIN, RIGHT JOIN, RIGHT OUTER JOIN, OUTER JOIN?

http://stackoverflow.com/questions/38549/difference-between-inner-and-outer-joins




4. Can a database have a table that cannot join to any other one, i.e. any INNER JOIN with the table always results in empty set? Explain why you think so.

Yes, if a table has no columns & not data in common with any of the
other tables, then an INNER JOIN with the table will always result in
the empty set.


5. How many JOIN clauses you need to get information from 6 tables?

5


6. Three tables: students, classes, registration.

first) Get all students in classA.

Don't know what this means.

a) Get all student not taking 'Physics' class.

select distinct(s.first_name) from student s
inner join registration r on s.id = r.student_id
inner join class c on r.class_id = c.id
where c.class_name != "Physics";


b) Find out who takes most classes

c) Find out which student doesn't take any class.
