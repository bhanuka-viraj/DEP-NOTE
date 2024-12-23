Literal => 

![[Pasted image 20240709185908.png]]

add code here

Operators => 

![[Pasted image 20240709190442.png]]

![[Pasted image 20240709190519.png]]

```Java
import jakarta.el.ExpressionFactory;  
import jakarta.el.StandardELContext;  
import jakarta.el.ValueExpression;  
  
public class ElOperators {  
    public static void main(String[] args) {  
        ExpressionFactory ef = ExpressionFactory.newInstance();  
        StandardELContext context = new StandardELContext(ef);  
        ValueExpression ve1 = ef.createValueExpression(context, "${10 + 5}", int.class);  
        int value1 = ve1.getValue(context);  
        System.out.println(value1);  
  
        ValueExpression ve2 = ef.createValueExpression(context, "${10 -5}", int.class);  
        int value2 = ve2.getValue(context);  
        System.out.println(value2);  
  
        ValueExpression ve3 = ef.createValueExpression(context, "${10+15.2}", float.class);  
        float value3 = ve3.getValue(context);  
        System.out.println(value3);  
  
        ValueExpression ve4 = ef.createValueExpression(context, "${10*2}", float.class);  
        float value4 = ve4.getValue(context);  
        System.out.println(value4);  
  
        ValueExpression ve5 = ef.createValueExpression(context, "${100 /2}", float.class);  
        float value5 = ve5.getValue(context);  
        System.out.println(value5);  
  
        ValueExpression ve6 = ef.createValueExpression(context, "${100 div 2}", float.class);  
        float value6 = ve6.getValue(context);  
        System.out.println(value6);  
  
        ValueExpression ve7 = ef.createValueExpression(context, "${11 % 2}", int.class);  
        int value7 = ve7.getValue(context);  
        System.out.println(value7);  
  
        ValueExpression ve8 = ef.createValueExpression(context, "${11 mod 2}", int.class);  
        int value8 = ve8.getValue(context);  
        System.out.println(value8);  
  
        ValueExpression ve9 = ef.createValueExpression(context, "${'ij'+='se'}", String.class);  
        String value9 = ve9.getValue(context);  
        System.out.println(value9);  
    }  
}
```

![[Pasted image 20240709174314.png]]

