
|                                                                    |                                                                                                                                                                                                       |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the use of <br>transient keyword                           | when use this keyword with a instace, it is  removed from  the serialization an deserialization process.<br><br>This is not only for java serialization. <br><br>![[Pasted image 20240405120707.png]] |
| ==can be static variable are <br>used with transient <br>keyword== | There is no compilation error.<br><br>But usually static are not used for serialization                                                                                                               |

How is the transient keyword is used.

```
import java.io.Serializable;  
  
public class Customer implements Serializable {  
    private int id;  
    private String name;  
    private transient String contact;  
  
    private static final long serialVersionUID = 6111497387916932307L;  
  
    static {  
        System.out.println("Customer class Object is being Initialized");  
    }  
  
    {  
        System.out.println("Customer instance is being initialized");  
    }  
  
    public Customer(int id, String name, String contact) {  
        this.id = id;  
        this.name = name;  
        this.contact = contact;  
        System.out.println("Customer instance has been just initialized");  
    }  
  
    @Override  
    public String toString() {  
        return "Customer{" +  
                "id=" + id +  
                ", name='" + name + '\'' +  
                ", contact='" + contact + '\'' +  
                '}';  
    }  
}
```

when the customer object is deserialized the output is ->

Customer class object is being initialized Customer
{id=1, name='Kasun', contact='null'} Customer{id=2, name='Sampath', contact='null'}

contact is null as it is not serialized, therefore not saved in the file.

if we make name transient even after serializing the object, when we deserialize, name will be null if run by giving serialVersionUID explicitly. This is the reason that is said "when the transient is used, variable is removed from both serialization and deserialization "

