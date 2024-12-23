![[Pasted image 20240709174047.png]]

```Java
import jakarta.el.ExpressionFactory;  
import jakarta.el.StandardELContext;  
import jakarta.el.ValueExpression;  
  
public class ElOperators2 {  
    public static void main(String[] args) {  
        ExpressionFactory ef = ExpressionFactory.newInstance();  
        StandardELContext context = new StandardELContext(ef);  
        int x = 10, y = 20;  
        context.getVariableMapper().setVariable("x", ef.createValueExpression(x, int.class));  
        context.getVariableMapper().setVariable("y", ef.createValueExpression(y, int.class));  
        ValueExpression ve1 = ef.createValueExpression(context, "${(x>y) ? 'ijse' : 'dep'}", String.class);  
        String value1 = ve1.getValue(context);  
        System.out.println(value1);  
    }  
}
```
