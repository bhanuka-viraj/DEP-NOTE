From specification -> 

An important goal of Jakarta Expression Language is to ensure it can be used in a variety of environments. It must therefore provide enough flexibility to adapt to the specific requirements of the environment where it is being used.

Class [`ELContext`](https://jakarta.ee/specifications/expression-language/5.0/apidocs/jakarta.el/jakarta/el/elcontext "class in jakarta.el") is what links the Jakarta Expression Language with the specific environment where it is being used. It provides the mechanism through which all relevant context for creating or evaluating an expression is specified.

When Jakarta Expression Language is used in a web container, the creation of `ELContext` objects is controlled through the underlying technology. For example, in Jakarta Server Pages, the `JspContext.getELContext()` factory method is used. In an stand-alone environment, a default [`StandardELContext`](https://jakarta.ee/specifications/expression-language/5.0/apidocs/jakarta.el/jakarta/el/standardelcontext "class in jakarta.el") is provided.

Some technologies provide the ability to add an [`ELContextListener`](https://jakarta.ee/specifications/expression-language/5.0/apidocs/jakarta.el/jakarta/el/elcontextlistener "interface in jakarta.el") so that applications and frameworks can ensure their own context objects are attached to any newly created `ELContext`.


linke -> https://jakarta.ee/specifications/expression-language/5.0/apidocs/jakarta.el/jakarta/el/package-summary


Note -> To evaluate the expression the expression context is required. When use with the web container context is given and no need to created. But when EL is used stand alone the context is need to be created. The values in the context are used for the evaluation. 