![[Pasted image 20240709134432.png]]


```Java
import java.lang.reflect.Constructor;  
import java.lang.reflect.InvocationTargetException;  
  
public class InvokePrivateConstructorDemo {  
    public static void main(String[] args) throws NoSuchMethodException, InvocationTargetException, InstantiationException, IllegalAccessException {  
        Constructor<Demo3> noArgsConstructor = Demo3.class.getDeclaredConstructor();  
        noArgsConstructor.setAccessible(true);  
        Demo3 demo3 = noArgsConstructor.newInstance();  
        System.out.println(demo3);  
    }  
}  
  
class Demo3 {  
    private Demo3() {  
        System.out.println("No one can invoke me");  
    }  
}
```
