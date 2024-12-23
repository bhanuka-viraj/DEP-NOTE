

#### Exact Mapping

#### Wild Card Mapping

#### Extension Mapping

#### Default Mapping

#### Context Mapping


#### Summary

These api are found in the HTTPServletRequest

These api does not depend with the mapping type. Give the same result for the all mapping type

`getRequestURL( )` => after removing the fragment and queries

`getReuquestURI()` =>

`getContextPath()` =>


![[Pasted image 20240702140602.png]]

These api are changed with the mapping type ->
`getServletPath()`
`getPathInfo()`


==Exact Mapping =>==  URL Pattern -> `/hello/abc`

![[Pasted image 20240702140412.png]]
==Context Mapping =>==

![[Pasted image 20240702141224.png]]

==Extension Mapping =>== url pattern -> `*.asiri`

![[Pasted image 20240702141612.png]]
`getPathInfo` is null here

==Wild Card Mapping== =>url pattern -> `/hello/*`
![[Pasted image 20240702142019.png]]


what is the common formula to find `getSevletPath()`
![[Pasted image 20240702143042.png]]

What are the mapping type that `getPathInfo()` null ->

->Exact Mapping
->Extension Mapping
->Default Mapping
->Some time in wild card mapping 


Examples ->

```plain
URL Pattern = /hello/dep/*

provided URL :- http://localhost:8080/app/hello/dep?q=abc&nam=kasun

getRequest URL -> http://localhost:8080/app/hello/dep

getRequest URI ->/app/hello/dep

getContextpath ->/app

getServletPath ->getURI - getContextPath - [*] => /hello/dep

getPathInfo -> getRequestURI - getContextPath - getServletPath -> null

=======================================================================

URL Pattern = /hello/dep/*

provided URL :- http://localhost:8080/app/hello/dep/#fragment

getRequest URL -> http://localhost:8080/app/hello/dep/

getRequest URI ->/app/hello/dep/

getContextpath ->/app

getServletPath ->getURI - getContextPath - [*] => /hello/dep

getPathInfo -> getRequestURI - getContextPath - getServletPath ->/

=======================================================================

URL Pattern = /

provided URL :- http://localhost:8080/app/hello/dep/#fragment

getRequest URL -> http://localhost:8080/app/hello/dep/

getRequest URI ->/app/hello/dep/

getContextpath ->/app

getServletPath ->getRequestURI - getContextPath - [*] => /hello/dep/

getPathInfo -> getRequestURI - getContextPath - getServletPath ->

=======================================================================

URL Pattern = *.png

provided URL :- http://localhost:8080/app/hello/test.png#123

getRequest URL -> http://localhost:8080/app/hello/test.png

getRequest URI ->/app/hello/test.png

getContextpath ->/app

getServletPath ->getRequestURI - getContextPath - [*] => /hello/test/png

getPathInfo -> getRequestURI - getContextPath - getServletPath -> null
```



