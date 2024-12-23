
|                                                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is the use of <br>singleton design pattern                    | To use the same object several time<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| What is the design pattern<br>category of singleton design pattern | creational design pattern                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| What are the two type of <br>singleton design pattern              | 1. Eagerly -><br>Whether if it is requested or not object is created<br>(created object when the singleton class is <br>initialized )<br><br>2. Lazily -><br>Object is created only when it is requested                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| What are the steps to create <br>singleton design pattern          | 1. Create private constructors<br><br>2.<br>Eagerly-><br>create reference<br>`private static final ClassName INSTANCE`<br>and assigned it with a object<br>(fully encapsulated class variable)<br><br>Lazily -><br>create reference<br>`private static ClassName INSTANCE`<br>(fully encapsulated class variable)<br><br>3.<br>Eagerly-><br>create method <br>`private static ClassName getInstance()`<br>and return the `INSTANCE` in this method<br>(api to expose the object)<br><br>Lazily -><br>create method<br>`private static ClassName getInstance() `<br>return `INSTANCE` assggning new object if it <br>is null. Otherwise return the `INSTANCE`<br>(api to expose the object) |


```public class Student {  
  
    //(2)Eagerly->  
    // private static final Student INSTANCE = new Student("1", "Kasun", "Galle");    
    //(2)Lazily-> private String id;  
    private static Student INSTANCE;  
    private String name;  
    private String age;  
  
    //(1)  
    private Student(String id, String name, String age) {  
        this.id = id;  
        this.name = name;  
        this.age = age;  
    }  
  
    //(3)  
    public static Student getInstance() {  
        //Eagerly-> return INSTANCE;  
  
        //Lazily-> return (INSTANCE== null) ? INSTANCE = new Student("1", "Kasun", "Galle") : INSTANCE;  
    }  
  
  
}
```
![[Pasted image 20240506182639.png]]

|                                                                                 |                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What are the <br>difference between <br>eagarly and lazily<br>singleton pattern | 1. Since the instance is created initially in eagerly ,<br>if the object is heavy weight then memory consumption is high<br><br>2.In lazily it is allowed to set the values for the object before it is created |
| How to create <br>singleton using a <br>inner class                             | ![[Pasted image 20240507140940.png]]                                                                                                                                                                            |


