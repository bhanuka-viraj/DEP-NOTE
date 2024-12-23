What is the purpose of using filters in the servlet -> 

Filters are called `middle wear`
Filters can manipulate both request and response before reach their destination. Not only for manipulation filters can be used to filter the request and response. This is not just a intercept. Commonly filters are used for security purpose.

How to add Filters to logical DD ->

Can be done using both annotation and web.xml.  If order of the filters are concerned web.xml is the only option. Because order of the filters cannot be managed through the annotation.

declaration order of the filters in the `web.xml` is the order of the filters are created

![[Pasted image 20240704001402.png]]

1.Using annotation ->
![[Pasted image 20240703142925.png]]

servlet-name can be used replacing the urlPatten. But there is a difference using serlvet name and url pattern. When order of the filters can be changed when using the servlet-name 

![[Pasted image 20240703143124.png]]

What is the filter chain ->

[[Filter Register Scanning]]
[[Filter Class hierarchy]]
[[Life Cycle of a Filter]]


