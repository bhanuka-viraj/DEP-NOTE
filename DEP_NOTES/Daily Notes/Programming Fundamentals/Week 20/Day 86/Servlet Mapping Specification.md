
#### Use of URL Paths

![[Pasted image 20240702115247.png]]

link for the specification =>
https://jakarta.ee/specifications/servlet/6.0/jakarta-servlet-spec-6.0#use-of-url-paths

#### Specification of Mapping / Order of Mapping

This is the order that is mapping the url when find the servlet from the registry. If one of below is matched, then not go for the next mapping

##### 1.Exact Mapping

=>All Exact Mapping should be started from the `/`

=>`Ex -> /xxxxx
=>`Ex -> /xxxxx/
=>`Ex -> /xxxx/xxx

In exact mapping check the exact path ->
`ikman.lk/property`
`ikman.lk/property/`

In lots of server above two are equal. But in the servlet this not same. Path should be equal exactly. Including the  `/` forward slash
##### 2.Wildcard Mapping

=>This is case sensitive

=>All Exact Mapping should be started from the `/`.
=>Should be ends with `*` 
=> `Ex-> /xxx/xxx/*`

the final part can be anything

Only the final segment can be anything
`Ex-. /xxx/xxxx/*/*`
In this case only last `*` is considered a wild card character.Matched url pattern should be like this `/xxx/xxx/*/xxx`
##### 3. Extension Mapping
=> should be like this `*.xxxxx`
=> anything can be in before but should be end with `.xxx`
=> This is not considered as extension mapping 
=> `/` cannot be in added in before
##### 4.Default Servlet Mapping
=> Should only have `/`
IF the request url is not mapped with the above mapping then matched with the default mapping

==What is default servlet ->==
The servlet that is included the default mapping is called as the default servlet

##### 5.Empty String Mapping
This is also called as context path mapping

This should be equal to the context path. If the context path `app` then matched path can be either `/app` or `/app/` in empty string mapping

