Many side is selected as the Owner end. Inverse end pk is taken to the owner end and set the `NOT NULL` constrain for it. If is there any attributes in the relationship they goes to the owner end. Totally participation of the one side is not handled by the data base and it should be handled by the application. Mapping is same as the previous case.

![[Pasted image 20240722103623.png]]

both customer and order should be persist inside the same transaction 

![[Pasted image 20240722104642.png]]

Didn't work properly... please check the customer class. Constructor should fixed.