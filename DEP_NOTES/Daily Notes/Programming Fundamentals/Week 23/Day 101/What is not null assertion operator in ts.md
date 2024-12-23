The non-null assertion operator (`!`) in TypeScript is used to tell the TypeScript compiler that a value is not null or undefined, even if TypeScript cannot infer that from the code. This operator is helpful when you, as the developer, are certain about the non-null nature of a variable, but TypeScript's type checking isn't able to determine that certainty.

without not null assertion operator -> 

Now there is a error because compiler does not guarantee that value not gonna be a null value. 
![[Pasted image 20240724182502.png]]

with null assertion operator -> 
whit the not null assertion property it is implicitly define that return not gonna be a null value.

![[Pasted image 20240724182536.png]]