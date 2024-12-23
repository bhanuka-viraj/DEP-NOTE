- **`@Component`**:
    
    - The most generic stereotype annotation.
    - Indicates that the annotated class is a Spring-managed component or bean.
    - Used when the component does not fit into any specific role (like service, repository, or controller).
- **`@Service`**:
    
    - Specialization of `@Component`.
    - Indicates that the annotated class is a service component.
    - Used to mark a class as a service layer in the application, typically containing business logic.
- **`@Repository`**:
    
    - Another specialization of `@Component`.
    - Indicates that the annotated class is a repository component.
    - Typically used for Data Access Objects (DAOs) that interact with the database.
    - Also has additional functionality related to exception translation in Spring's data access framework.
- **`@Controller`**:
    
    - Specialization of `@Component`.
    - Indicates that the annotated class is a web controller in a Spring MVC application.
    - Used to handle HTTP requests and responses.