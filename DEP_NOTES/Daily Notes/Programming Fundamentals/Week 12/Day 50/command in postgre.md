

|           |                                                                                                             |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| \c        | to get the connected data base<br>and connect with the data bases when put the <br>database name at the end |
| \conninfo | to get the connection info with the connected port                                                          |
| \q        | to exit from the postgre                                                                                    |
| \l        | to get the list of available data bases                                                                     |
| \x        | to turn on / off expanded display                                                                           |
| \d        | [pattern] List Everything                                                                                   |
| \dt       | List Relation                                                                                               |
| \dv       | List View                                                                                                   |
| \di       | List Indexe                                                                                                 |
| \df       | List procuderes / triggers/ funcitons                                                                       |
|           |                                                                                                             |


|                                                      |                                                                 |
| ---------------------------------------------------- | --------------------------------------------------------------- |
| How to create a data base<br>using postgre terminal  | create database <database_name>;<br>                            |
| How to delete a data base <br>using postgre terminal | drop database <database_name>;                                  |
| How log to postgre                                   | `psql -h localhost -p 12500 -U postgres -W`                     |
| How to create db in <br>one command                  | `createdb -h localshost -p 12500 -U postgres -W <datbase name>` |
