
|                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| what is the reason <br>to use resource bundle                         | To store the configurations                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| how look like a <br>resource bundle                                   | ![[Pasted image 20240507164902.png]]<br>not allowed add space with equal `=`<br># for comment<br><br>should be included with the key and value pairs                                                                                                                                                                                                                                                                                                                                                                         |
| What are the type of resources                                        | Internal and External resources<br><br>Internal -> resources that are will be included to the artifact<br>External ->                                                                                                                                                                                                                                                                                                                                                                                                        |
| how to create link<br>with internal resource                          | There are two ways to do this-><br><br>non-static-><br>getClass( ).getResource (" ") : return URL<br>getClass( ).getResourceAsStream(" ") : Input Stream<br><br>static -><br>ClassName.class.getResource(" "): return URL<br>ClassName.class.getResourceAsStream(" ") : Input Stream                                                                                                                                                                                                                                         |
| how to make link with external resources                              | new File(" ") : File<br>Paths.get(" ") : Path<br>Path.of(" ") : Path                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| what is the structure of a JAR file<br><br>Explain this               | ![[Pasted image 20240507174848.png]]<br><br>when create the jar file META-INF, internal resources and all source code in main directory are included to the jar file<br><br>(mvn package)                                                                                                                                                                                                                                                                                                                                    |
| What are the archive file types                                       | JAR - Java Archive <br>WAR - Web Archive <br>EAR - Enterprise Archive                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| what is the <br>MANIFEST.MF                                           | The MANIFEST.MF file is a metadata file in Java JAR (Java ARchive) files. It contains information about the JAR file itself, including:<br><br>Manifest-Version: The version of the manifest file specification.<br>Created-By: The tool used to create the JAR file.<br>Main-Class: The entry point class for standalone applications.<br>Class-Path: Specifies other JAR files or directories containing classes needed by the application.<br>Dependencies: Additional metadata such as version numbers or library names. |
| How to add classpath to the <br>MANIFEST.MF<br>using pom.xml file     | ![[Pasted image 20240507174213.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| How to add main<br>class to the <br>MANIFEST.MF<br>using pom.xml file | ![[Pasted image 20240507174330.png]]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Why MANIFEST.MF is<br> important<br>                                  | to find the entrypoint of the application for the JVM                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| How to set the configure<br>file where located in internet            | Set the configuration file in internet. set the link as he URL<br><br>![[Pasted image 20240507182340.png]]                                                                                                                                                                                                                                                                                                                                                                                                                   |
| what is the reason to<br>use prefix when create the properties        | ![[Pasted image 20240507184325.png]]<br>this is used to mitigate the possible conflict that can be arises when the other key,value pairs comes to the resource bundle<br><br>Resource Bundle properties + OS env user + JRE env                                                                                                                                                                                                                                                                                              |
refer this link in apache maven->
https://maven.apache.org/plugins/maven-jar-plugin/