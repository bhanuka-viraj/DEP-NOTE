
## tsconfig.json configurations 

==What is the use of `target`== => 
Set the version of the js that ts going to converted. 


==What is the use of `module`== => 
Set the module system that gonna used


==What is the user of `root`== => 
Set the directory of the `main.ts` file

==What is the use of `outDir`== => 
Set the directory that compiled file (main.js) that gonna stored.

==What is the use `useUnknownInCatchVariables` in tsconfig.json => ==

In js and ts anything can be thrown. It is not necessary be a error.Number , string or anything can be thrown. When `useUnknownInCatchVariables` is true catch parameter data type is set to `unknown`. So type assertion should be done before use the catch parameter in the catch clause. 

![[Pasted image 20240725115744.png]]

What is the reason to set false  to `useUnknownInCatchVariables`. =>

This is a good feature but unnecessary for a large scale project. If we set this to false then data type of the catch parameter is set to the any. Then no need to do the type assertion every time. So if we can code with the a good discipline only throwing errors, `useUnknownInCatchVariables` set to false it make easier to code. 

==What is the use of `noEmitOnError`== => 

if this true then it minimize running the code if there are is a compilation error.It means the if there are some errors when compile this directory not gonna created.