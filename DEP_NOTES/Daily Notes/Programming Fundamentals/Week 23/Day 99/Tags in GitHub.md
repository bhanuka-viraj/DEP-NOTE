
|                                                 |                                                                                                                                                                                                                     |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the purpose <br>of using tags in github | This is used to add extra information about the commit<br><br>This help to find the special moments of a commits                                                                                                    |
| How to attached a<br>tag                        | First it is neceessary to know the has code of the commit<br><br>to get the has code -> <br>`git tag` => list all tags<br><br>then run this command -> <br><br>`git tag <version> [ commit Sha value]` <br><br><br> |
| What is the <br>convention of the version       | v1.0.0                                                                                                                                                                                                              |
| What is the use of <br>tags                     | Tag name can be use as the identifier of the commit.<br>It can be used to travel through the time line                                                                                                              |
| Why tag is used                                 | Tags are usually used when release a version<br>add the version number                                                                                                                                              |
| Are tags  pushed                                | In default tags are not pushed to the repository<br><br>use this command to push tags <br>`git push <remote> <tag name>`                                                                                            |
| What are the type of <br>tags in git            | 1. Light Weight Tags<br>2. Annotated Tags<br><br><br>This note about the light weight tags<br>                                                                                                                      |
| What are the annotated<br>tags                  | Annotated tags are used to describes the lightweight tags<br><br>How to create a annotated tags<br><br>`git tag -a <tag name> [<commit sha value> = HEAD] "<message>"`                                              |

What are the meaning of this commands 

`git tag` -> to get all attached tags
\
`git tag <version> [Sha value]` -> To attached a tag (in default sha value is the value of head)

`git show <tag name>` -> to get the information about the tag

`git show --name-only <tag name>` -> obtain the information and only show the 
changed file name

`git show --name-status <tag name>` -> obtain the information and show the status ( A - Add, M - Modified, D - Delete, R - Rename)

`git tag -d <tag names>` -> to delete tags

`git push <remote> <tag name>` -> to push tag into cloud

`git push <remote> --tags` -> to push all tags together

`git tag -a <tag name> [<commit sha value> = HEAD] "<message>"` -> to create annotated tags


