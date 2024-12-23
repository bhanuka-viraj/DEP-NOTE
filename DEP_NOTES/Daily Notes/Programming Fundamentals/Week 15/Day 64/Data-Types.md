
|           |                                                                                                                                                                                  |
| --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Boolean   | literals -> true / false                                                                                                                                                         |
| number    | for numbers, both floating and primitive<br>literals -> binary ,octal, decimal, hexadecimal<br><br>There are two way to represent octal<br>old way -> `080`<br>new way -> `0o80` |
| string    | <br><br>literals  ->`' '`, `" "`, `~ ~`<br><br>the string that is used with `~ ~`  is called non taged template <br>string                                                       |
| undefined | use js engine to say no                                                                                                                                                          |
| null      | use developers to say no                                                                                                                                                         |
| symbol    | to use things encapsulate                                                                                                                                                        |
| bigint    | represent numbers.Only for primitive numbers<br><br>allow to do calculate between bigInt, but not with numbers<br>                                                               |
examples for bigint

```JS
console.log(100n);  
console.log(50n);  
console.log(25n + 25n);
```


|                                                             |                                                                                                                                                                                                             |
| ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the difference <br>between null and undefined       | There is a difference between undefined and null. Developer use null and js use undefined                                                                                                                   |
| What are the new <br>data types                             | Symbol and bigint were introduced in 2015.                                                                                                                                                                  |
| Is it allowed to use <br>hexadecimal for <br>floating point | No. It is not allowed to use. Only decimal can be used as the floating point                                                                                                                                |
| What is the difference between `' '`  and `" "`             | There is no difference. But it allow to use single quote in double quote and double quote in single<br>quote without using ecape characters                                                                 |
| what is the text <br>interpolation syntax                   | <br>![[Pasted image 20240528170213.png]]                                                                                                                                                                    |
| what is the difference <br>between `==` and `===`           | `==` determines the value equality, `===` determines the value and type equality<br><br>also there are similar property as `!=` `!==`<br>                                                                   |
| what is the support for <br>js for decimals                 | since numbers use IEEE-754 for floating points, the precision is low. There is no data type similar to <br>the big decimal java. <br><br>Library from the outside are used for it<br>`decimal.js`, `big.js` |
|                                                             |                                                                                                                                                                                                             |
