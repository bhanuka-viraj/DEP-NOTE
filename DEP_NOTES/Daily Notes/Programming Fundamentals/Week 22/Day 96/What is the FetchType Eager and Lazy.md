Default values of  `@OneToOne` ,`@ManyToOne`, `@OneToMany`, `@ManyToMany`


|               | Default Fetching Mechanism |
| ------------- | -------------------------- |
| `@OneToOne`   | Fetch = Eager              |
| `@ManyToOne`  | Fetch = Eager              |
| `@OneToMany`  | Fetch = Lazy               |
| `@ManyToMany` | Fetch = Lazy               |


### Fetch Types

#### Eager Fetching

- **Definition**: Eager fetching loads the associated entities immediately when the  entity is loaded.
- **Behavior**: When an entity with an eager relationship is retrieved, all associated entities are also retrieved in the same query.
- **Use Case**: Suitable when you always need the related entities along with the parent entity.
#### Lazy Fetching

- **Definition**: Lazy fetching delays the loading of the associated entities until they are explicitly accessed.
- **Behavior**: When an entity with a lazy relationship is retrieved, the associated entities are not loaded immediately. They are loaded only when they are accessed for the first time.
- **Use Case**: Suitable when you do not always need the associated entities and want to avoid the performance overhead of loading them.

When the associate entity has one entity , always default fetching type is `Eager`, 
(OneToOne and ManyToOne)

if the associate entity has more than one entity it default fetching type is `Lazy`
(ManyToMany and OneToMany)