
| While | For | do-While |
| ---- | ---- | ---- |
| This is a pretest loop | This is a pretest loop | This is post-test loop |
| syntax: <br>while boolean [statement];<br><br> | syntax:<br>for ([initalizer] ; [boolean]; [update])[statement];<br><br>![[Pasted image 20240206113335.png]]<br> | syntax:<br><br>for 1 statement=><br>do statement; while(boolean_expression)<br><br>for multiple statement =><br>do {<br>    statement(s);<br>}while(boolean_expression) |
| *statement is optional *<br> | *initializer, boolean and update are optional here. All elements are optional* | *any element in do-while loops is not optional* |
| execution flow:<br><br>1.check the condition first,<br><br>2 if true => execute the statement<br>    when the boolean expression is false, then exist form <br>    the loop | execution flow:<br><br>![[Pasted image 20240206114121.png]]<br><br>(1) first run the initialization<br>(2)check the boolean expression<br>(3) run the statement <br>(4) run the update<br><br>(2)check the boolean expression<br>(3)run the statement<br>(4)run the update<br>(2)check the boolean expression<br><br>This continue until boolean false | execution flow:<br><br>![[Pasted image 20240206163622.png]]<br><br>(1) first run the statement<br>(2) check the condition<br><br>if condition true execute the statement, when the boolean false exist from the loop.<br> |

