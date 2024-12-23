
|                                                                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is the reason <br>to introduce this                                    | To find the solution for the problem of  finally block                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [[demo-29]]                                                                 | What is the risk of using finally or what is the difference between finally and resource statement<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| What are the resources that can be used <br>try with resource <br>statement | The members that are ==implemented from the AutoClosable== can be use as the resources<br><br>When they are used it is not required to close the resource explicitly                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| What is closeable                                                           | Closseable was introduced in java 1.5. The exception of the closealbe is IOException.  It is  included in the java.io paccakge in java se.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| What is the difference<br>between<br>Closeable and <br>AutoCloseable        | AutoCloseble was introudced in java 1.7 (java 7) under java lang package. java lang can be used in the any kind of java runtime environment. This is the reason why Autoclsable was introduced.<br><br>When the Autoclosable was introduced there were lot of resources was created using the closeable. To use the closeable  it is extened from AutoClosable. The exception of the AutoClosable is Exception. <br><br>Since the exception of the Sub class is a sub exception of the super class exception it can be used without any error according to the overriding rules. This is the reason why Closeable was created as the subclass<br><br>![[Pasted image 20240319184511.png]] |
| demo-30<br><br>What is the order of resources<br>closing                    | Reverse order of the resource created                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Is it allowed to declare the resource<br>outside from the try catch         | yes. It was introduced since java 9                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
demo- 29
```
import java.io.Closeable;
import java.io.IOException;

public class AppInitializer {

    public static void main(String[] args) throws Exception {
        System.out.println(myMethod2());
    }

    static int myMethod1() throws Exception {
        Resource1 res1 = new Resource1();
        Resource2 res2 = new Resource2();
        try {
            System.out.println(res1);
            System.out.println(res2);
            return 10;                  // R=10
        } finally {
            res1.close();
            res2.close();
        }
    }

    static int myMethod2() throws Exception {
        try (Resource1 res1 = new Resource1();
             Resource3 res3 = new Resource3();
             Resource2 res2 = new Resource2()) {
            System.out.println(res1);
            System.out.println(res2);
            return 10;
        }finally{
            System.out.println("This is try..with..resource statement");
        }
    }
}

class Resource1 implements AutoCloseable {
    @Override
    public void close() throws Exception {
        System.out.println("Resource1 is about to close");
    }
}

class Resource2 implements AutoCloseable {
    @Override
    public void close() throws Exception {
        System.out.println("Resource2 is about to close");
    }
}

class Resource3 implements Closeable {
    public void close()throws IOException {
        System.out.println("Resource3 is about to close");
    }
}
```

demo - 30
```
public class AppInitializer {

    public static void main(String[] args) {
        Resource1 res1 = new Resource1();
        Resource2 res2 = new Resource2();
        try(res1; res2){
            System.out.println(res1);
            System.out.println(res2);
        } catch (Exception e) {
            System.out.println("Something went wrong while closing");
        } finally{
            System.out.println("Try..with..resource statement");
        }
    }

}
class Resource1 implements AutoCloseable{
    @Override
    public void close() throws Exception {
        System.out.println("Resource1 is being closed");
    }
}
class Resource2 implements AutoCloseable{
    @Override
    public void close() throws Exception {
        System.out.println("Resource2 is being closed");
    }
}
```
