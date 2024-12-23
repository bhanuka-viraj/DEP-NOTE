
![[Pasted image 20240715115741.png]]
### Cardinality Ratio in Databases

**Cardinality ratio** in the context of databases refers to the numerical relationship between two tables/entities in a database. It defines how many instances of one entity can be associated with instances of another entity. Understanding cardinality ratios is essential for accurately modeling the relationships between tables in a database schema. There are three primary types of cardinality ratios:

1. **One-to-One (1:1)**:
    
    - **Definition**: Each instance of entity A is associated with exactly one instance of entity B, and vice versa.
    - **Example**: Each employee has one unique company ID, and each company ID corresponds to one employee.
	    ![[Pasted image 20240716015244.png]]
2. **One-to-Many (1**
    
    **)**:
    
    - **Definition**: Each instance of entity A can be associated with zero, one, or many instances of entity B, but each instance of entity B is associated with exactly one instance of entity A.
    - **Example**: A single customer can place multiple orders, but each order is placed by one customer.
    
      ![[Pasted image 20240716015419.png]]
    - 
      
3. **Many-to-Many (M**
    
    **)**:
    
    - **Definition**: Each instance of entity A can be associated with multiple instances of entity B, and each instance of entity B can be associated with multiple instances of entity A.
    - **Example**: Students and courses, where a student can enroll in multiple courses, and each course can have multiple students enrolled.
      
      ![[Pasted image 20240716015400.png]]