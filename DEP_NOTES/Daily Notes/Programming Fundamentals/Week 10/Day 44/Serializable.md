Java object serializable

|                                                                        |                                                                                                                                                                                                                                                                                                                                                                         |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ==What is serialization==<br><br>very common<br>interview <br>question | In computing, serialization (or serialisation) is the process of translating a data structure or object state into a format that can be stored (e.g. files in secondary storage devices, data buffers in primary storage devices) or transmitted (e.g. data streams over computer networks) and ==reconstructed== later (possibly in a different computer environment). |
| ==What is desirialization==                                            | Extracting a data structure from a series of bytes, is deserialization,                                                                                                                                                                                                                                                                                                 |
| ==What is marshalling==                                                | This process of serializing an object is also called [marshalling](https://en.wikipedia.org/wiki/Marshalling_(computer_science) "Marshalling (computer science)") an object in some situations                                                                                                                                                                          |
| ==What is unmarshalling==                                              | The process of desirialization in object                                                                                                                                                                                                                                                                                                                                |
| ==What is java Object serialization==                                  | Translating object in to bytes.                                                                                                                                                                                                                                                                                                                                         |
| What is the reason in java object being called first class citizen.    | Get the most priorities.                                                                                                                                                                                                                                                                                                                                                |
| What is tagging<br>/ Maker interface                                   | Marker Interface is a empty interface.(explain more)<br><br>Java serialization process works only with classes that tagged with interface serializable (implement with serializable)                                                                                                                                                                                    |
| How to make class eligible for java serialization                      | Java serialization process works only with classes that tagged with interface serializable (implement with serializable)<br><br>==Object Input streams and Object output streams are used for the serialization==                                                                                                                                                       |
| What is the use of Object input streams                                | collect the bytes to a object<br>(read the bytes and reconstruct the object)                                                                                                                                                                                                                                                                                            |
| What is the use of Object Output<br>streams                            | Write bytes in objects<br>(check this)                                                                                                                                                                                                                                                                                                                                  |


Serialization ->

![[Pasted image 20240405093838.png]]

```
import java.io.ByteArrayOutputStream;  
import java.io.IOException;  
import java.io.ObjectInputStream;  
import java.io.ObjectOutputStream;  
import java.util.Arrays;  
  
public class SerializationDemo {  
    public static void main(String[] args) throws IOException {  
        Employee employee = new Employee(1, "Kasun", "Galle");  
  
        ByteArrayOutputStream baos = new ByteArrayOutputStream();  
        ObjectOutputStream oos = new ObjectOutputStream(baos);  
  
        oos.writeObject(employee);  
        byte[] byteArray = baos.toByteArray();  
        System.out.println(Arrays.toString(byteArray));  
    }  
}
```

|                                               |                                                                                                                                                                                                                                                        |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| How does the Object input streams work        | two socket are given to object from JVM similar to the os is give to files<br><br>But need a something to take the bytes from <br>Object output stream <br><br>serialize states and other bytes that need to reconstruct the object<br><br>complete... |
| What is the usage of byte array output stream | Store the byte comes from the Object output stream                                                                                                                                                                                                     |

Deserialization ->
![[Pasted image 20240405094058.png]]


```
import java.io.ByteArrayInputStream;  
import java.io.IOException;  
import java.io.ObjectInputStream;  
  
public class Deserialization {  
    public static void main(String[] args) throws IOException, ClassNotFoundException {  
        byte [] employeeObjects = {-84, -19, 0, 5, 115, 114, 0, 8, 69, 109, 112, 108, 111, 121, 101, 101, 39, -6, 14, -66, 71, 46, -45, -112, 2, 0, 3, 73, 0, 2, 105, 100, 76, 0, 7, 97, 100, 100, 114, 101, 115, 115, 116, 0, 18, 76, 106, 97, 118, 97, 47, 108, 97, 110, 103, 47, 83, 116, 114, 105, 110, 103, 59, 76, 0, 4, 110, 97, 109, 101, 113, 0, 126, 0, 1, 120, 112, 0, 0, 0, 1, 116, 0, 5, 71, 97, 108, 108, 101, 116, 0, 5, 75, 97, 115, 117, 110};  
  
        ByteArrayInputStream bais = new ByteArrayInputStream(employeeObjects);  
        ObjectInputStream objectInputStream = new ObjectInputStream(bais);  
  
        Object o = objectInputStream.readObject();  
        System.out.println(o);  
  
    }  
}
```


|                                                                                               |                                                                                                                                                                                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How does the Object output<br>stream works                                                    | complete...                                                                                                                                                                                                                                                                                                                                        |
| ==What is the only time in java<br>that constructor is not executed<br>when create a object== | In deserializtion                                                                                                                                                                                                                                                                                                                                  |
| how does the bytes store where<br>comes from the input strem                                  | in a empty object                                                                                                                                                                                                                                                                                                                                  |
| Is it required the blue print to <br>create the instance<br>(deserialization)                 | Yes. Byte is included the all the data to identify the blue print.<br><br>==The constructor is not executed when the object is created==<br><br>This is the only time constructor is not executed <br>when initialize the object.<br><br>All process apart from the constructor execution <br>other are same as  the class instance creation. <br> |
| What is the reason to <br>constructor is not being<br>used to initialize the object           | If the constructor is used to initialize the object<br>then it become a new object (instance)<br><br>But we need clone the same object that was  serialized.<br>This why constructor is not being used to <br>initialize the object                                                                                                                |

