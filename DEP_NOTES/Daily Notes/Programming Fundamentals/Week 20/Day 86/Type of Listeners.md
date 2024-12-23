
`ServletContextListner` -> when selvlet context is initialized and destroyed
`ServletContextAttributeListener` -> When  data  created, updated, stored in servlet context
`ServletRequestListner`-> When request is created and end
`ServletRequestAttributeListner` -> When  data  created, updated, stored in a request
`HttpSessionListner` -> When session is created and destroyed
`HttpSessionAttributeListner` -> When  data  created, updated, stored in a session

### Types of Servlet Listeners:

1. **ServletContextListener**:
    - Monitors the lifecycle events of the servlet context (application-wide scope).
    - Methods: `contextInitialized()`, `contextDestroyed()`.
2. **HttpSessionListener**:

    - Monitors the lifecycle events of HTTP sessions.
    - Methods: `sessionCreated()`, `sessionDestroyed()`.
3. **ServletRequestListener**:
    
    - Monitors the lifecycle events of servlet requests.
    - Methods: `requestInitialized()`, `requestDestroyed()`.
4. **ServletRequestAttributeListener**:
    
    - Monitors changes to attributes in servlet requests.
    - Methods: `attributeAdded()`, `attributeRemoved()`, `attributeReplaced()`.
5. **HttpSessionAttributeListener**:
    
    - Monitors changes to attributes in HTTP sessions.
    - Methods: `attributeAdded()`, `attributeRemoved()`, `attributeReplaced()`.
6. **ServletContextAttributeListener**:
    
    - Monitors changes to attributes in the servlet context.
    - Methods: `attributeAdded()`, `attributeRemoved()`, `attributeReplaced()`.
    


