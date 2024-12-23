
|                                                   |                                                                                                     |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| What is the reason<br>to use cascade              | Do the same execution for the associated entitiees                                                  |
| What doe mean the<br>dirty persistence<br>context | Is there at least one entity that the dirty flag is true, then<br>the persistence context is dirty. |
|                                                   |                                                                                                     |

### Cascade Types

1. **CascadeType.PERSIST**
    
    - **Behavior**: When the parent entity is persisted (saved), the related entities are also persisted.
    - **Use Case**: Useful when you want to automatically save new related entities when the parent entity is saved.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.PERSIST) private Set<Order> orders;`
        
2. **CascadeType.MERGE**
    
    - **Behavior**: When the parent entity is merged (updated), the related entities are also merged.
    - **Use Case**: Useful when you want to automatically update related entities when the parent entity is updated.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.MERGE) private Set<Order> orders;`
        
3. **CascadeType.REMOVE**
    
    - **Behavior**: When the parent entity is removed (deleted), the related entities are also removed.
    - **Use Case**: Useful when you want to automatically delete related entities when the parent entity is deleted.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.REMOVE) private Set<Order> orders;`
        
4. **CascadeType.REFRESH**
    
    - **Behavior**: When the parent entity is refreshed, the related entities are also refreshed.
    - **Use Case**: Useful when you want to reload the state of related entities from the database.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.REFRESH) private Set<Order> orders;`
        
5. **CascadeType.DETACH**
    
    - **Behavior**: When the parent entity is detached, the related entities are also detached.
    - **Use Case**: Useful when you want to detach related entities from the persistence context along with the parent entity.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.DETACH) private Set<Order> orders;`
        
6. **CascadeType.ALL**
    
    - **Behavior**: Applies all the cascade operations (PERSIST, MERGE, REMOVE, REFRESH, DETACH) to the related entities.
    - **Use Case**: Useful when you want all operations to be cascaded to the related entities.
    - **Example**:
        
        java
        
        Copy code
        
        `@OneToMany(cascade = CascadeType.ALL) private Set<Order> orders;`