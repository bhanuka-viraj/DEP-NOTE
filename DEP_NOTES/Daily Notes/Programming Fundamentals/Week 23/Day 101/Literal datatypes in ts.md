In TypeScript, literal data types allow you to specify the exact values a variable can hold. 


It is not necessary to use the same date type in the literal data types\

![[Pasted image 20240724151448.png]]

why it is called literal data type -> Because it is used already existing data types in js




These are specific types of values and can be categorized into different types:
### String Literals

String literal types allow you to specify a set of strings that a variable can hold.

typescript

Copy code

`type Direction = "north" | "south" | "east" | "west";  let move: Direction; move = "north";  // Valid move = "up";     // Error: Type '"up"' is not assignable to type 'Direction'.`

### Numeric Literals

Numeric literal types restrict a variable to hold a set of specific numbers.

typescript

Copy code

`type StatusCode = 200 | 404 | 500;  let status: StatusCode; status = 200;  // Valid status = 403;  // Error: Type '403' is not assignable to type 'StatusCode'.`

### Boolean Literals

Boolean literal types are restricted to the values `true` and `false`.

typescript

Copy code

`type YesOrNo = true | false;  let answer: YesOrNo; answer = true;  // Valid answer = false; // Valid answer = "yes"; // Error: Type '"yes"' is not assignable to type 'YesOrNo'.`

### Example Combining Literals

Literal types can be combined using union types to create more complex types.

typescript

Copy code

`type CardinalDirection = "north" | "south" | "east" | "west"; type ResponseCode = 200 | 404 | 500; type Flag = true | false;  type Config = {   direction: CardinalDirection;   status: ResponseCode;   isActive: Flag; };  let config: Config = {   direction: "north",   status: 200,   isActive: true };`

### Advantages

- **Type Safety**: Ensures that variables hold only the allowed literal values.
- **Documentation**: Makes it clear which values are permitted.
- **Error Prevention**: Helps catch errors at compile time rather than runtime.
- 