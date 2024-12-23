What are the step to create Entity Class (when the Table is already created)

step1 ->  Create the class with the table name. Then crate the fields that match with the table rows(use the same data type)

step 2 ->
Add the `@Entity` annotation before the class. Implement the class with the `serializable`. add annotaion `@DATA`, `@NoArgsConstructor`, `@AllArgsConstructor`.

Entity class should be followed the bean specification.

step 3-> Use `@Column` annotation if some naming conflict there between table columns and fields of the entity class.
Use `@Table` if some naming conflict there between entity class and table

Note -> The Entity class should be followed the bean specification

![[Pasted image 20240711113504.png]]