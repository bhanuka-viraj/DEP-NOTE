

What is the difference between events listeners in web api in JQueryj

In Web api the event is set only one time if the event is set the multiple time using the same function reference. But in Jquery it is set all the time with same function reference


|                                                                             |                                                                                                           |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `$().on("eventname",callbackFn)`                                            | To add event listners                                                                                     |
| `$().off("eventname",callbackFn[calbakFnReferecne])`                        | To remove event listeners<br><br>if the reference is not defenied then remove the all event <br>listeners |
| `$(fixed parent element).on("eventname", "valid css selector",callback fn)` | This is how set the delegated event listners                                                              |
| `$().trigger("eventname")`                                                  | to trigger a event<br>through coding                                                                      |
![[Pasted image 20240620121844.png]]