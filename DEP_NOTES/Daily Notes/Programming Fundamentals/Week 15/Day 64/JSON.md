
|                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is JSON stand for                                              | JavaScript Object Notation<br>Jason has a shape of a java script object                                                                                                                                                                                                                                                                                                                                                                                            |
| What is JSON                                                        | JSON is a collection of key - value pairs                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Why JSON is bieng used                                              | To structure the data                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| what are the options <br>for the make data structure                | XML<br>JSON<br>YAML                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| What are the benefit <br>of data structures                         | to store data and transfer data                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Is JSON same as java <br>script objects                             | No. It has the shape of the js object. But not equal to <br>the js object                                                                                                                                                                                                                                                                                                                                                                                          |
| What are the <br>characteristic of JSON                             | Key should be a string.<br><br>String should be wrap up using double quote<br><br>Comments are not allowed within the json<br><br>Only one json object can be created in a one source<br>code. But allow to have json objects within the json<br>object as values<br><br>date should be added as in string type<br><br>naming convention is camel case<br><br>Array can be used in a json file instead a json object<br><br>Not allowed to have identical keys<br> |
| What can be contained<br>in a json file to be a <br>valid json file | if only one of below can be contained in a valid json<br>file<br><br>`"String"`<br>`number`<br>`true`<br>`flase`<br>`null`<br>`[ ]`<br>`{}`                                                                                                                                                                                                                                                                                                                        |
| what is a minimal <br>package.json                                  | The minimum requirement of a json file to include <br>in node package. If the package json is valid but <br>not contain the minimal requirement then it is not<br>considered as a package.json file. Also the <br>package is not considered as a valid node package                                                                                                                                                                                                |
| what are the requrement<br>for the minimal <br>package.json         | ![[Pasted image 20240528115631.png]]                                                                                                                                                                                                                                                                                                                                                                                                                               |

example for json object (json object can contain a another json object as a  value)
```JSON
{
"id":"C001",
"name":"Kasun",
"dob":"2000-01-01",
"age":3,
"status":false,
"contact":["077-1234567","011-1234578"],
"salary":null,
"key1":"string",
"address":{
"number" :"208",
"city":"Panadura",
"country":"Sri Lanka",
"postalCode":12500
}
}
```


What can be used as the `value` for JSON

![[Pasted image 20240528111330.png]]
In here object and array are json array and object, not the js objects

In Json array allow to have difference type of data unlike java

example for a minimal  package.json ->
```JSON
{
"name":"package-1",
"verson":"1.0.0"
}
```

example for a package.json file
![[Pasted image 20240528131913.png]]

|                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[npm commands]]                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| How to add <br>dependcies into the<br>node package                                            | add the dependency list in to the package.json file                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| note                                                                                          | npm can resolve transitive dependencies                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| is it required to<br>give node_modules<br>for someone with the source code or <br>push to git | no. It is not required. It is need to be installed using <br>`npm i` command. Since the package.json is there no need of share the node_module <br>                                                                                                                                                                                       ![[Pasted image 20240528130412.png]]<br><br>`^` -> minor version updates ok<br>`~` -> patch version updates ok(also can be added x at the end)<br> |
| what is the meaning <br>of this                                                               | ![[Pasted image 20240528130834.png]]<br>Using this signs it allows to set the how should version <br>of the packages should be changed with the version updates                                                                                                                                                                                                                                                                                                                              |
| what is the script in json files                                                              | this script can be executed using the command <br>`npm run <script name>`                                                                                                                                                                                                                                                                                                                                                                                                                    |
| what does mean <br>main in package.json                                                       | the entry point                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |


