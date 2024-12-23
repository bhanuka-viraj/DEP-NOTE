Try this sql injections with 'sql-injection' project

query -> 

```SQL
SELECT full_name FROM "user" WHERE username = 'user' AND password = 'password'
```

try this sql injections

username = kasun'--
username = fhjfw OR true

==Use prepared statement with user input to prevent SQL Injections==


|                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what can be done <br>to prevent the SQL<br>Injection | 1.When the password or user name are entered false  don't <br>tell the users to what is exact wrong one. Also don't give <br>focus to the exact wrong field (when log to account)<br><br>2.When enter to password do not specify what is wrong <br>with the password(letter missing, character missing)<br><br>3.Take the user name and password separately(don't take<br>them in a single UI). <br>Don't check them using one query.<br><br>4.Use prepared statement instead regular expression<br> |
