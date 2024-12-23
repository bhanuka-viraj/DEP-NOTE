### Participation in DBMS

**Participation** in the context of Database Management Systems (DBMS) refers to the extent to which entities are involved in a relationship in an Entity-Relationship (ER) model. It indicates whether all or only some instances of an entity participate in a relationship. There are two main types of participation:

1. **Total Participation (Mandatory Participation)**:
    
    - **Definition**: Every instance of the entity must participate in the relationship.
    - **Symbol**: Denoted by a double line connecting the entity to the relationship in the ER diagram.
    - **Example**: In a university database, suppose every student must be enrolled in at least one course. Here, the participation of the "Student" entity in the "Enrollment" relationship is total.
2. **Partial Participation (Optional Participation)**:
    
    - **Definition**: Some instances of the entity may not participate in the relationship.
    - **Symbol**: Denoted by a single line connecting the entity to the relationship in the ER diagram.
    - **Example**: In a company database, not every employee is necessarily a manager. Here, the participation of the "Employee" entity in the "Manages" relationship is partial.