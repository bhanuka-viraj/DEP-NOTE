
|                                                |                                      |
| ---------------------------------------------- | ------------------------------------ |
| How to make a class <br>to a iterable in java  | implementing the class with iterable |
```Java
package lk.ijse.dep12;  
  
import java.util.Iterator;  
import java.util.List;  
import java.util.Spliterator;  
import java.util.function.Consumer;  
  
public class Demo {  
    public static void main(String[] args) {  
        //For Each, Enhanced For Loop  
        int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};  
        for (int number : numbers) {  
            System.out.println(number);  
        }  
  
        List<String> nameLIst = List.of("Kausn", "Nuwan", "Supun");  
        for (String name : nameLIst) {  
            System.out.println(name);  
        }  
  
        //Array and List are in default implement with the iterable Interface  
  
        var customer = new Customer("C001", "Kausn Sampath", new String[]{"071-1234567", "011-7654321"});  
        for (String contact : customer) {  
            System.out.println(contact);  
        }  
  
    }  
}  
  
class Customer implements Iterable<String> {  
    String id;  
    String name;  
    String[] contactList;  
  
    public Customer(String id, String name, String[] contactList) {  
        this.id = id;  
        this.name = name;  
        this.contactList = contactList;  
    }  
  
    @Override  
    public Iterator<String> iterator() {  
        return new Iterator<String>() {  
            int i = 0;  
  
            @Override  
            public boolean hasNext() {  
                return contactList.length != i;  
            }  
  
            @Override  
            public String next() {  
                return contactList[i++];  
            }  
        };  
    }  
  
}
```


How does the `for(String contact : customer){sout(contact)}`

```Java
Iterator<String> iterator = customer.iterator();  
while (true) {  
    if (!iterator.hasNext()) break;  
    var value = iterator.next();  
    System.out.println(value);  
}
```

