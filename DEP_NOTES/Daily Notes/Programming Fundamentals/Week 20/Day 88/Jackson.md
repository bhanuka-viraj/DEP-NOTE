maven repository get jackson data bind-> https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind/2.17.1

jackson databind spec -> https://github.com/FasterXML/jackson-databind


|                                                     |                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the purpose<br>of using jackson             | allow to convert java object to json and json to java object                                                                                                                                                                                                                                                                                                        |
| how does the bean<br>spec affect for the<br>jackson | If the the class does not follow the bean spec then no <br>args constructor and all args constructor should be added<br>(at leas no arg constructor)<br><br><br>if cannot add a no args constructor then object should be<br>added to a hash map<br><br>![[Pasted image 20240705113925.png]]<br><br>if the data order is concerned then use a link hash map instead |
| what is the bean<br>specification                   |                                                                                                                                                                                                                                                                                                                                                                     |
| Is jackson thread<br>safe                           | Yes. It thread safe                                                                                                                                                                                                                                                                                                                                                 |
| what is the use of<br>this -><br>                   | `serializationFeature.INDENT_OUTPUT`<br><br>This used to add some indent and white spaces json object<br>to fix it formatting                                                                                                                                                                                                                                       |
| What is the use<br>of object mapper                 | Facilate the conversion between Java objects and JSON data, allowing for easy serialization (Java objects to JSON) and deserialization (JSON to Java objects).                                                                                                                                                                                                      |

`java object to json =>`

![[Pasted image 20240705113226.png]]

`json to object =>`
![[Pasted image 20240705120223.png]]

==Q.== How to change the jason key value to required conventions. In default it comes the way it define in the class (camel case) =>

==A.== Use `JsonProperty`
![[Pasted image 20240705120346.png]]

==Q.== How to ignore a property of a object when convert it into a Json -> 

==A.== Use `JsonIgnore`

![[Pasted image 20240705121039.png]]

[[How to convert json list to a array]]
[[How to works Jackson with  Local Date]]


