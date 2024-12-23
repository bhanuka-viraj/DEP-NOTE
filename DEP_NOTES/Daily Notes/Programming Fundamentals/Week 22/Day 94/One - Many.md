
![[Pasted image 20240717123219.png]]


[[How to decompose Cardinaty]]

==1.When Only Many side is participated totally==
customer is partially participated and order totally participated
![[Pasted image 20240717231258.png]]

Set the totally participation as the owner end and passed the inverse end primary key as the foreign key.Then set the `NOTNULL` constrain for it. (Not set the `UNIQUE`)

db script ->

![[Pasted image 20240717125226.png]]

ORM mapping -> 

Customer class->
![[Pasted image 20240717130358.png]]

Order Class ->

![[Pasted image 20240717130422.png]]

How to make this bidirectional ->

Initially set a list , and the this is replaced by the `PersistanceBag`

The same problems that arise when bidirectional is used with the One-One  are occurred in here too.

How to solve them ->

```Java
@Data  
@NoArgsConstructor  
@Entity  
@ToString(exclude = "orders")  
//solving the toString issue  
@Table(name = "customer")  
public class Customer implements Serializable {  
    @Id  
    private String contact;  
    private String name;  
    private String address;  
    @OneToMany(mappedBy = "customer", cascade = {CascadeType.PERSIST, CascadeType.DETACH})  
    /*Solving the setter method issue*/  
    @Setter(AccessLevel.NONE)  
    private List<Order> orders = new ArrayList<>();  
  
    /*Solving the all args constructor issues*/  
    public Customer(String contact, String name, String address, List<Order> orders) {  
        if (orders != null && !orders.isEmpty()) {  
            orders.stream().filter(order -> order.getCustomer() == null).forEach(order -> order.setCustomer(this));  
        }  
  
        if (orders != null && !orders.isEmpty()) {  
            orders.forEach(order -> {  
                if (order.getCustomer() != this)  
                    throw new IllegalStateException("An Order:%s is already associated with an another customer"  
                            .formatted(order.getId()));  
            });  
        }  
        this.contact = contact;  
        this.name = name;  
        this.address = address;  
        this.orders = orders;  
    }  
  
    public Customer(String contact, String name, String address) {  
        this.contact = contact;  
        this.name = name;  
        this.address = address;  
    }  
}

```

solving the constructor issues ->

![[Pasted image 20240717134149.png]]

[[What is the FetchType Eager and Lazy]]

How does FetchType Eager and Lazy works ->
![[Pasted image 20240717141917.png]]

![[Pasted image 20240717141945.png]]
Explanation -> 

In this one-many relationship order is the many side and customer is the one side. A order has one customer. When order is loaded, the customer is loaded `eagerly`.This is whey selected is executed for  the `em.find(Order.class, "OD001)`. When customer is loaded orders of the customer are loaded `lazily`. Because order is in many side and the default fetch type is `lazy`.Second select is executed for this. Third Select is executed when the muditha's orders are iterated. Kajja already came to the persistence context when the `od001` is loaded. No required of a select query for this. Fourth select query is executed when the kajja's orders are iterated.

[[What are the cascade type]]
[[Entity Listeners and call back methods]]
[[What is persistence bag]]
[[Mapping Rules for One to Many]]

