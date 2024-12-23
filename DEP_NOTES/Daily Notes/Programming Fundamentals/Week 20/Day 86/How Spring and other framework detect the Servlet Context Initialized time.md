`contextInitialized()` method of the `AppContextListner` is doesn't give the exact time of the servlet context initialized

So there is a special way to do that => 

refer this link of the servlet specification =>
https://jakarta.ee/specifications/servlet/6.0/jakarta-servlet-spec-6.0#shared-libraries-runtimes-pluggability

```Plain
#### 8.2.4. Shared Libraries / Runtimes Pluggability

In addition to supporting fragments and use of annotations, one of the requirements is that not only we be able to plug-in things that are bundled in the `WEB-INF/lib` but also plugin shared copies of frameworks - including being able to plug-in to the web container things like Jakarta XML Web Services, Jakarta Restful Web Services and Jakarta Server Faces that build on top of the web container. The `ServletContainerInitializer` allows handling such a use case as described below.

The `ServletContainerInitializer` class is looked up via the jar services API. For each application, an instance of the `ServletContainerInitializer` is created by the container at application startup time. The framework providing an implementation of the `ServletContainerInitializer` MUST bundle in the `META-INF/services` directory of the jar file a file called `jakarta.servlet.ServletContainerInitializer`, as per the jar services API, that points to the implementation class of the `ServletContainerInitializer`.

In addition to the `ServletContainerInitializer` we also have an annotation - `HandlesTypes`. The `HandlesTypes` annotation on the implementation of the `ServletContainerInitializer` is used to express interest in classes that may have annotations (type, method or field level annotations) specified in the value of the `HandlesTypes` or if it extends / implements one those classes anywhere in the class’s super types. The `HandlesTypes` annotation is applied irrespective of the setting of `metadata-complete`.

When examining the classes of an application to see if they match any of the criteria specified by the `HandlesTypes` annotation of a `ServletContainerInitializer`, the container may run into class loading problems if one or more of the application’s optional JAR files are missing. Since the container is not in a position to decide whether these types of class loading failures will prevent the application from working correctly, it must ignore them, while at the same time providing a configuration option that would log them.

If an implementation of `ServletContainerInitializer` does not have the `@HandlesTypes` annotation, or if there are no matches to any of the `HandlesType` specified, then it will get invoked once for every application with `null` as the value of the `Set`. This will allow for the initializer to determine based on the resources available in the application whether it needs to initialize a servlet / filter or not.

The `onStartup` method of the `ServletContainerInitializer` will be invoked when the application is coming up before any of the servlet listener events are fired.

The `onStartup` method of the `ServletContainerInitializer` is called with a `Set` of Classes that either extend / implement the classes that the initializer expressed interest in or if it is annotated with any of the classes specified via the `@HandlesTypes` annotation.

A concrete example below showcases how this would work.

Let’s take the Jakarta XML Web Services web services runtime.

The implementation of Jakarta XML Web Services runtime isn’t typically bundled in each and every war file. The implementation would bundle an implementation of the `ServletContainerInitializer` (shown below) and the container would look that up using the services API (the jar file will bundle in it’s `META-INF/services` directory a file called `jakarta.servlet.ServletContainerInitializer` that will point to the `JAXWSServletContainerInitializer`
```

This is the time that spring is started

==Interview Question => ==

Q. Does Spring detect the app initialized time through servlet event -> 
A. No. It is not a consistent way to do that. `SerlvetContainerIntializer` class is used instead.
