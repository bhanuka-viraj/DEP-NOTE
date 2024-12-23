Class object is loaded in the deployment ->

Then create a instance of a filter using the singleton design pattern and then execute the `init` method. Now this is graduated as a filter. ->

Now spend majority of time to provide service (doFilter()) method ->
Then destory



The life cycle of the filter is almost same as the servlet. only change is that servlet can be loaded in both during the deployment and when getting the first request.But filters are loaded only during the deployment. 

![[Pasted image 20240704001535.png]]

![[Pasted image 20240703152311.png]]
comparison of the life cycle between filters and servlets
