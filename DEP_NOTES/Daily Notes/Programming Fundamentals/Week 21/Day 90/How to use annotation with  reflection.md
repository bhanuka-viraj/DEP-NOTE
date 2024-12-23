
```Java
import java.lang.reflect.Field;  
import java.lang.reflect.InvocationTargetException;  
import java.lang.reflect.Method;  
  
@Dep12(startingDate = "2024-01-01")  
public class ReflectionWithAnnotationDemo {  
  
    @Dep12(startingDate = "2024-01-23")  
    static String startingDate;  
  
    @Dep12(duration = 8, startingDate = "2024-01-24")  
    static void printDep12Details(int duration, String startingDate) {  
        System.out.println("Duration: " + duration);  
        System.out.println("Starting Date: " + startingDate);  
        System.out.println("exucuted");  
    }  
  
    public static void main(String[] args) throws NoSuchFieldException, IllegalAccessException, NoSuchMethodException, InvocationTargetException {  
        Dep12 classAnnotation =  ReflectionWithAnnotationDemo.class.getDeclaredAnnotation(Dep12.class);  
        System.out.println(classAnnotation.startingDate());  
        System.out.println(classAnnotation.duration());  
        System.out.println("---------------------------");  
        System.out.println(startingDate);  
        Field dateField = ReflectionWithAnnotationDemo.class.getDeclaredField("startingDate");  
        Dep12 declaredAnnotation = dateField.getDeclaredAnnotation(Dep12.class);  
        dateField.set(ReflectionWithAnnotationDemo.class, declaredAnnotation.startingDate());  
        System.out.println(startingDate);  
        System.out.println("---------------------------");  
        /*Catch method using reflection*/  
        Method printDep12Details = ReflectionWithAnnotationDemo.class.getDeclaredMethod("printDep12Details", int.class, String.class);  
        /*Catch the annotation using reflection*/  
        Dep12 declaredAnnotation1 = printDep12Details.getDeclaredAnnotation(Dep12.class);  
        printDep12Details.invoke(ReflectionWithAnnotationDemo.class, declaredAnnotation1.duration(), declaredAnnotation1.startingDate());  
  
    }  
  
}
```

==Q.== What is the reason to use  `ReflectionWithAnnotationDemo.class` inside `invoke()` method. 

==A.== This contain both static and no static method. `ReflectionWithAnnotationDemo.class` is used denote this is a static method. If the method is a instance method then reference of the instance should be passed instead.

`printDep12Details.invoke(ReflectionWithAnnotationDemo.class, declaredAnnotation1.duration(), declaredAnnotation1.startingDate());`

![[Pasted image 20240709161401.png]]

