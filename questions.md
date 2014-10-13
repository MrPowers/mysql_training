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
