![[Pasted image 20240709115308.png]]


All Class object are instance of the `Class class object`.`Class class object` is extend with the `Object class object`.So it cannot say that who is created first between this two. So `Class class object` and `Object class object` are created natively.

Instance of the Demo class is created from the `DemoClass Class object`. Like that `DemoClass Class Object` is a instance of the `Class class object`. So non static method of the Class class objects inherit to the DemoClass class object.

`class` is a static variable kind of thing (generated using native, this is called literal class) in `DemoClass class object`. But the `class` variable not found in the `Class class object`. 
`class` variable refer the `Class class object`. Also the `getClass( )` method return the `Class class Object.` So following code return true

`System.out.println(Demo.class == new Demo().getClass());`

But when create a another class called customer and check following codes it returns false.

```Java
 System.out.println(Customer.class == Double.class);
 System.out.println(new Customer().getClass() == new Demo().getClass());
```

This is because  class variable of the `DemoClass Object` and `getClass` method of the Demo instance refer the `Class class Object` it self. Reflection api of the `Class class object` are comes to the any class object that is in the method area. `getClass()` or `class (class literal)` is used to access reflection api.

reflection apis which are in the `Class class object` are executed through the `DemoClass class object`. The is called `delegation`.


reflection api -> https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Class.html

![[Pasted image 20240709131619.png]]


following api pattern is common for all reflection api
`Declare` ->All without concerning access modifier but without inheritance

|                     |                                                                                                          |
| ------------------- | -------------------------------------------------------------------------------------------------------- |
| `getMethods`        | Show methods withing the class all without concerning the access modifier.Not return the inherit methods |
| `getFields`         | Show only public fields. But show the inherited fields.                                                  |
| `getDeclaredFields` | Show feilds withing the class all without concerning the access modifier.Not return the inherit fields   |

[[Changing a value of a private variable using reflection]]
[[How to invoke a private method using reflection]]
[[Obtain a value of  a private variable]]
[[Creating a instance using a private constructor using refleciton ]]
[[How to use annotation with  reflection]]

