==Q.==What is the difference when using the object from `Class` and `Records` and what is the impact of  `@Data` from [[Lombok]] when use with the `hashMap`

==A.==
add the github link for this -> 

Record -> In default override the `equals()` and `hashcode()`
`@Data` represent the `@equalsAndHashcode` in lombok

`@equalsAndHashCode` has overridden the `equals()` and `hashCode()`

When use the record or class with the `@Data` duplicate objects are not get for the `HashMap`. But it is not used the one of above two then get the duplicate

When object has overridden the `equls()` and `hashCode()` hashMap can determine it should be stored or where it should be stored. 

If Records or class with `@Data` not used and also need to use with the hasMap then `hashCode()` and `equals()` need to be overridden. 

In String `hashCod()` and `equals()` methods have been overridden in default.


[[What is the reason to use equals rather == to comparing object]]

[[How does the hashMap use hashcode( ) and equals( )]]

Methods in Object class -> 
![[Pasted image 20240708225447.png]]

|                                                     |                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the reason to <br>override the `hashCode()` | To work correctly the object with the hashing algorithm.<br>If the object is not required work with the hash code <br>it is not required to override it.<br><br>If it is not override then give it's default behavior.<br>Default `hashCode` give the memory location. Not the <br>hash code |

![[Pasted image 20240708225505.png]]

|                                   | By default behavior and reason for the override it                                                                        |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| getClass                          | In Reflection                                                                                                             |
| hashCode                          | Default ->Object Memory Location<br>Override -> To use with the hashing alogorithm                                        |
| toString                          | Default -> hexa decimal hash code<br>Override ->To obtain the string representation of the object state                   |
| equals(Object)                    | Default -> check the equality of the memory location<br>Override -> To check the equality of the states of object(fields) |
| Notify()<br>NotifyAll()<br>Wait() | for concurrency programmin                                                                                                |
| finalize                          | with garbage collector                                                                                                    |
| Clone                             | To clone object (need extend with clonable)                                                                               |
