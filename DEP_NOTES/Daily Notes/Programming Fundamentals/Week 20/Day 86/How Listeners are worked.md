
`AppContextLIstner` ->

![[Pasted image 20240703125537.png]]

After servlet context is initialized  instances of listeners  are created before filters and servlets. First `AppContextListner` instance is created among any other Listeners. This is singleton.  So only one instance is created. But can have multiple `AppContextListner`. After `AppContextListner` is created then `servletContextEvent` object is created and it is linked with the servlet context. This object is passed to the `contextIntialzed()` method when it is created. This is the same process like `serlvetConfigObject` in servlet. After servlet context is destroyed again another `servletConntextEvent` object is created  and it is linked with the serlvet context. Then  it is passed to the `contexDestroyed` method of the `AppContextListner` to invoked.

`RequestLinstner` ->

![[Pasted image 20240703233702.png]]

`RequestListner` object is created after initialize the servlet context

This explanation should be added to just before the thread search the servlet path from the servlet registry after found the app using context path. Before search the servlet registry `serlvetRequestEvent` instance is created. Then it is linked with the both context servlet and `HTTPServletRequestImpl` instance. Then `serlvetRequestEvent` is passed to the `requistInitialized` method of the `RequestListner` instance. So using `requestInitalized` method both servlet context and request can be accessed. When response is unwrapped to the web server (this is consider as the request is destroyed) another `servletRequestEvent`  instance is created and it is linked with the both servlet context and   request. The `servletRequestEvent` instance is passed to the `requestDestroyed()` method of the `HTTPServletRequestImpl` instance.