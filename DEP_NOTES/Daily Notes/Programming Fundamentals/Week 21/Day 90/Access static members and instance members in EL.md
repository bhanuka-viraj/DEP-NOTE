
Q.How to access the static members (properties / methods) -> 

```java
package lk.ijse.dep12;  
  
import jakarta.el.ExpressionFactory;  
import jakarta.el.StandardELContext;  
import jakarta.el.ValueExpression;  
  
public class StaticMember {  
    public static void main(String[] args) {  
        ExpressionFactory ef = ExpressionFactory.newInstance();  
        StandardELContext context = new StandardELContext(ef);  
        context.getImportHandler().importPackage("lk.ijse.dep12");  
        var value = ef.createValueExpression(context, "${StaticMember.add(10,20)}", int.class).getValue(context);  
        System.out.println(value);  
  
    }  
  
    public static int add(int x, int y) {  
        return x + y;  
    }  
  
}
```


Only dot notation can be used to access for static members


Q. How to access the instance members -> 

![[Pasted image 20240709192854.png]]

```Java
package lk.ijse.dep12;  
  
import jakarta.el.ExpressionFactory;  
import jakarta.el.StandardELContext;  
  
public class instanceMembers {  
    public static void main(String[] args) {  
        ExpressionFactory ef = ExpressionFactory.newInstance();  
        StandardELContext context = new StandardELContext(ef);  
        context.getImportHandler().importPackage("lk.ijse.dep12");  
        context.getVariableMapper().setVariable("c1",  
                ef.createValueExpression(new Customer(1,"Kasun"),Customer.class));  
        Object value = ef.createValueExpression(context, "${c1['name']}", String.class).getValue(context);  
  
        System.out.println(value);  
  
    }  
}
```

Notes for instance  ->
If the property is accessed then bean spec should be followed. This is not issue for when access methods. 

To access the instance both `.` notation and `[]` can be used.

