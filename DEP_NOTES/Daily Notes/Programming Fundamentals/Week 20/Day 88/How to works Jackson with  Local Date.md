
==Q.== How to change the pattern of a `Date` property
==A.== user `@JsonFormat`

![[Pasted image 20240705125810.png]]

==Q.== How to enable support for the `Local Date` for json
==A.== In default json does not work with local date

refer this doc -> 
https://github.com/FasterXML/jackson-modules-java8/tree/2.18/datetime

mapper should be used with a `JsonMapper`

![[Pasted image 20240705130549.png]]
