
This is not used stand alone usually(But can be used stand alone if necessary). This is used with other specifications. But cannot be used with all specifications. This helps to minimize the lines of code need to write.

link for the specification -> https://jakarta.ee/specifications/expression-language/5.0/jakarta-expression-language-spec-5.0

|                                                                                   | Jakarta Expression Language -Jakarta EL                                                                                                                                    |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the reason <br>Jakarta EL is being  used with <br>jakarta bean validation | ==This  can be used to display advance dynamic error messages instead static error messages.==<br><br>Also it can be displayed error message without using this<br>        |
| What is the syntax that is <br>used with the <br>jakarta bean validation          | There are two syntaxes jakarta EL ->`${expr}` and`#{expr}`<br><br>jakarta bean validation use `${expr}`<br><br>Example -> <br><br>![[Pasted image 20240708115822.png]]<br> |
==Note== -> Now it is necessary to add dependency of `Expression Language` when use the `Jakarta Validation` to the application even if jakarta EL is not used  for dynamic error displaying. Because in default dependencies are checked. 

![[Pasted image 20240708121239.png]]
link to get the dependecy -> https://docs.jboss.org/hibernate/stable/validator/reference/en-US/html_single/#validator-gettingstarted-createproject

also available in mvn repository ->
https://mvnrepository.com/artifact/org.glassfish.expressly/expressly/5.0.0

[[Jakarta Expression Language Context]]

[[What are the expression type in the Expression Language]]

|                                    |                    |
| ---------------------------------- | ------------------ |
| What is the entry point <br>of the | Expression factory |
[[How to use collections EL]]
[[Literal and operators in EL]]
[[How to set the variables to the EL context]]
[[Access static members and instance members in EL]]
