Class A ->
```
public class ClassA {  
    int a;  
  
    static {  
        System.out.println("ClassA : Static Initializer");  
    }  
  
    {  
        System.out.println("ClassA : Instance Initializer");  
    }  
  
    public ClassA(int a) {  
        this.a = a;  
        System.out.println("ClassA : Constructor");  
    }  
  
    @Override  
    public String toString() {  
        return "ClassA{" +  
                "a=" + a +  
                '}';  
    }  
}
```

Class B -> 

```
import java.io.Serializable;  
  
public class ClassB extends ClassA {  
    int b;  
  
    static {  
        System.out.println("ClassB: Static Initializer");  
    }  
  
    {  
        System.out.println("ClassB: Instance Initializer");  
    }  
  
    public ClassB(int a, int b) {  
        super(a);  
        this.b = b;  
        System.out.println("ClassB: Constructor");  
    }  
  
    @Override  
    public String toString() {  
        return "ClassB{" +  
                "b=" + b +  
                '}' + super.toString();  
    }  
}
```

Class C ->

```
import java.io.Serializable;  
  
public class ClassC extends ClassB implements Serializable {  
    int c;  
  
    static {  
        System.out.println("class C: Static Initializer");  
    }  
  
    {  
        System.out.println("Class C: Instance Initializer");  
    }  
  
    public ClassC(int a, int b, int c) {  
        super(a, b);  
        this.c = c;  
  
    }  
  
    @Override  
    public String toString() {  
        return "ClassC{" +  
                "c=" + c +  
                '}' + super.toString();  
    }  
}
```


![[Pasted image 20240407002507.png]]
Case 1 :

=> Only ClassC has been implemented by the Serializable interface
=> This is serialized without any problem

=>In the deserialization process ( reconstruct the object)

Here constructor of C class is not run and it is necessary to initialize the whole three part of the class. But to initialize the super parts of object, it needs to run constructors of super class. If there is not a no arg constructor in class B in this situation, a error is encountered. 

ClassB with a no args constructor => 

With this implementation any error will not be encountered. 
```
import java.io.Serializable;  
  
public class ClassB extends ClassA {  
    int b;  
  
    static {  
        System.out.println("ClassB: Static Initializer");  
    }  
  
    {  
        System.out.println("ClassB: Instance Initializer");  
    }  
  
    public ClassB() {  
        super(50);  
        System.out.println("ClassB: No Arg Constructor");  
    }  
  
    public ClassB(int a, int b) {  
        super(a);  
        this.b = b;  
        System.out.println("ClassB: Constructor");  
    }  
  
    @Override  
    public String toString() {  
        return "ClassB{" +  
                "b=" + b +  
                '}' + super.toString();  
    }  
}
```

Case 2: 

=> When ClassB are implemented by Serializable interface both B and C parts are serialized. 
=> This serialized without any problem

=> In the deserialization process (reconstruct the object)
Here the constructors of both ClassC and Class B are not run. So "no args constructor" is required to ClassA to deserialize. Since ClassB is implemented by the Serializable interface no args constructor is now not required. 

Case 3:

=>If class A implement with the serializable ( most super ) then whole object A,B,C parts are serialized and can deserialize without any issue even if there is not a no arg constructor in any of the classes, as constructor does not need to run in A,B or C when reconstructing the object.


|                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Where serializable <br>should add into <br>a class hierarchy                                                                                                        | The most super class should be implements from the serializable.                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| What is the <br>reason to use <br>==externalizable== and how <br>use it.                                                                                            | ==When super class is not implemented by serializable and there is no "no arg constructor"  we can use externalizable to take the all control of serialization and deserialization.==<br><br>When the externalization is used all the control of the serialization and the deserialization is comes to our hand<br><br>When the externalization is used serializable is not worked any more.<br><br>No need to implement any class from Serializable<br><br>Implement most sub class by Externalizable Interface |
| What are the two method given to use the externalizable and <br>what is the use of them<br>(these methods are unimplemented methods<br>in externalizable interface) | public void wirteExteranal( ObjectOutput out){<br><br>}<br><br>public void readExternal(OjbectInput in){<br><br>}<br><br>These method are use for serialization and deserialization<br><br>                                                                                                                                                                                                                                                                                                                      |
|                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
The ClassC is implemented by the externalizable interface =>

```
import java.io.Externalizable;
import java.io.IOException;
import java.io.ObjectInput;
import java.io.ObjectOutput;

public class ClassC extends ClassB implements Externalizable {
    int c;

    static {
        System.out.println("ClassC: Static Initializer");
    }

    {
        System.out.println("ClassC: Instance Initializer");
    }

    public ClassC(int a, int b, int c) {
        super(a, b);
        this.c = c;
        System.out.println("ClassC: Constructor");
    }

    public ClassC() {
        System.out.println("ClassC : no arg constructor");
    }

    @Override
    public String toString() {
        return "ClassC{" +
                "c=" + c +
                '}' + super.toString();
    }

    @Override
    public void writeExternal(ObjectOutput out) throws IOException {
        out.write(c);   // done during serialization
        out.write(b);
        out.write(a);
    }

    @Override
    public void readExternal(ObjectInput in) throws IOException, ClassNotFoundException {
        c = in.read(); // done during deserialization
        b = in.read();
        a = in.read();
    }
}

```

=> It is necessary to have a no args constructor in ClassC

|                                                                              |                                                                      |
| ---------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| What is the use of<br>writeExternal( )                                       | This is done during the serialization. Write the values of variables |
| What is the use of<br>readExternal( )                                        | This is done during deserialization. Read the values of variables    |
| What is the reason <br>to have no args <br>constructor in most derived class |                                                                      |
|                                                                              |                                                                      |

=>When the externalizable is used default serializable feature  are not available. And also here we have to manually read and write all variables. 

=>To avoid this, we can implement from Serializable and override writeObject and readObject methods.

|                                                                                                                     |                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the two methods<br>that are provided in serializable<br>to use when the super class is<br>not serializable | private void writeOjbect(ObjectOutputStream oos){ }<br><br>private void readObject( ObjectOutputStream oos){ }<br><br>using this methods we can customize the java <br>default serialization / deserialization process |

=> In Here C part is serialized , B and A are not serialized. 

```
import java.io.*;

public class ClassC extends ClassB implements Serializable {
    int c;

    static {
        System.out.println("ClassC: Static Initializer");
    }

    {
        System.out.println("ClassC: Instance Initializer");
    }

    public ClassC(int a, int b, int c) {
        super(a, b);
        this.c = c;
        System.out.println("ClassC: Constructor");
    }

    public ClassC() {
        System.out.println("ClassC : no arg constructor");
    }

    @Override
    public String toString() {
        return "ClassC{" +
                "c=" + c +
                '}' + super.toString();
    }

    private void writeObject(ObjectOutputStream oos) throws Exception {
        oos.defaultWriteObject(); 
        // part of C is automatically written(parts that comes with defalult serialization)
        
        oos.write(b); // manually write
        oos.write(a); // manually write
    }

    private void readObject(ObjectInputStream ois) throws Exception {
        ois.defaultReadObject(); 
        // part of C is automatically read (parts that comes with default seriaization)
        b = ois.read(); //manually read
        a = ois.read(); //manually read
    }

}

```

|     | Serializable + wrteObject( ) +<br> readOjbect( )                                                                                                                                                                    | Externalizable                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
|     | Allow to customize the java<br>default serialization /<br>deserialization process<br>                                                                                                                               | Allow completely override the default <br>serialization / deserialization process                 |
|     | If the super class is not <br>serializable , then it should have<br>the no args constructor.<br>Otherwise the default deserialization<br>will fail even though it works fine <br>with default serialization process | Subclass should have the no arg<br>constructor, otherwise again the <br>deserialization will fail |
