
![[Pasted image 20240806130337.png]]

|                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the three <br>type of reset in git                  | `--soft`<br>`--mixed`<br>`--hard`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| What is the default<br>reset type in git                     | `--mixed`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| what is the syntax                                           | `git reset [reset type] <commits Value>`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| what is the use of <br>``soft``                              | ==This is used for the squashing==<br>A soft reset in Git is used to move the HEAD and branch (pointer) to a previous commit<br>without altering the working directory or the index, allowing you to rework commits and preserve your changes for further modifications.<br><br>What is squashing -><br>Squashing in Git is used to combine multiple commits into a <br>single commit to create a cleaner, more readable, and more manageable commit history.<br><br>This is to remove the mistakes in the previous commits<br><br>This reset the local repository<br><br> |
| what is the <br>use of <br>`mix`                             | ==This is used to restore the indexing stage==<br><br>Mix reset in Git is used to move the HEAD and branch to a previous commit<br>and update the indexing stage                                                                                                                                                                                                                                                                                                                                                                                                           |
| What is the <br>use of `hard`                                | ==This is used to restore for both indexing stage and the working <br>directory==<br><br>Hard reset in Git is used to move the HEAD and branch to a previous commit<br>and update the both indexing stage and the working directory                                                                                                                                                                                                                                                                                                                                        |
| What is the difference <br>between <br>restore and <br>reset | Restore is used to restore a certain file and reset is used to <br>restore the entire project based on a certain commit (whole file system)                                                                                                                                                                                                                                                                                                                                                                                                                                |
|                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

SOFT ->

How does the `soft` work -> 
before soft-> 
![[Pasted image 20240806132237.png]]

`git reset --soft ae81b00`

after soft ->
![[Pasted image 20240806132545.png]]

What is the squash commit -> 
the last commit that is committed after the  `soft`

![[Pasted image 20240806132747.png]]

MIX -> 

All with the soft and additionally update the indexing stage

HARD -> 

All with the MIX and additionally update the working directory




