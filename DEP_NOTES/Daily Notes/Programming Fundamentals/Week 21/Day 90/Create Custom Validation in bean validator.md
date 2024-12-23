Steps to create a custom validation ->

This is the class that is going to be validated in this example

```Java
public class User {  
    @NotBlank  
    @Pattern(regexp = "^[A-Za-z ]+$", message = "${ValidateValue} is not a valid name")  
    private String fullName;  
    @NotBlank  
    @Email    private String email;  
    @NotBlank  
    @Password private String password;  
    @Birthday()  
    @NotNull  
    private LocalDate birthday;  
}
```

Step 1 ->
create required `@annotaion` for the password validation and set the  retention policy to the `RUNTIME`. Add the following attributes to the annotation. Use a default validate annotation to find them. Including these attributes to a annotation is compulsory.

![[Pasted image 20240710083613.png]]

Step 2 ->
Create a class for the validation logic and implement it from the  `ConstraintValidator <(name of the annotation), (date type of the property)>` 

in above example ConstraintValidator would be like this ->
`CosntraintValidator <Password, String>`

![[Pasted image 20240710084905.png]]

Step 3 ->

Now create the link between `annotaion` and the `validotor` adding the `Contraint()` meta annotation to the annotation.

![[Pasted image 20240710085318.png]]

<hr>
<hr>

==How to Invoke a methods in Jakarta Validator when use the Expression Language==

Note -> In Jakarata Validation by default method are not allowed invoke when using the expression language. This is has done due to the security reason. Because the validatedValue is input by the user. 

to allow to invoke method following configuration need to be done-> 

In here validation is done using the `buildDefaultValidatorFacotry()`
![[Pasted image 20240709204552.png]]


```Java
public class UserValidationDemo {  
    public static void main(String[] args) {  
        User user1 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", LocalDate.now());  
//        User user2 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", );  
        User user3 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", LocalDate.of(1995, 2, 10));  
  
        try (ValidatorFactory vf = Validation.buildDefaultValidatorFactory()) {  
            Validator validator = vf.getValidator();  
            Set<ConstraintViolation<User>> violentSet = validator.validate(user1);  
            if (violentSet.isEmpty()) {  
                System.out.println("User is valid");  
            } else {  
                System.out.println("User is not valid");  
                violentSet.forEach(System.out::println);  
            }  
        }  
    }  
}
```

The expression language feature level should be changed and the `byProvider()` is need to be used.

![[Pasted image 20240710090227.png]]

```Java
  
public class UserValidationDemo {  
    public static void main(String[] args) {  
        User user1 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", LocalDate.now());  
//        User user2 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", );  
        User user3 = new User("Kasun Sampath", "kasun@ijse.lk", "Kaus12", LocalDate.of(1995, 2, 10));  
  
        try (ValidatorFactory vf = Validation.byProvider(HibernateValidator.class).configure().  
                constraintExpressionLanguageFeatureLevel(ExpressionLanguageFeatureLevel.BEAN_METHODS  
                ).buildValidatorFactory()  
        ) {  
            Validator validator = vf.getValidator();  
            Set<ConstraintViolation<User>> violentSet = validator.validate(user1);  
            if (violentSet.isEmpty()) {  
                System.out.println("User is valid");  
            } else {  
                System.out.println("User is not valid");  
                violentSet.forEach(System.out::println);  
            }  
        }  
    }  
}

```

`add the code need to be done in the @birthday`

<hr>
<hr>

This is about how to invoke methods in web container EL context

[[Default  Context in Expression Language]]
