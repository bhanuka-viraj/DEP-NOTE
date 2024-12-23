![[Pasted image 20240709133823.png]]

```Java
public class ObtainPrivateVariableValueDem {  
    public static void main(String[] args) throws NoSuchFieldException, IllegalAccessException {  
        Field dontTouchMe = Demo2.class.getDeclaredField("dontTouchMe");  
        dontTouchMe.setAccessible(true);  
        int value = (int) dontTouchMe.get(Demo2.class);  
        System.out.println(value);  
  
    }  
}  
  
class Demo2 {  
    private static int dontTouchMe = 5;  
}
```
