
|                                                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is an OS environment <br>variable                                           | Named value stored within the operating system's environment that can affect the behavior of processes and applications running on that system.<br><br>                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ==What is the objective of<br>OS environment varialbes==                         | Theese are can be access from any app that is run in the Os.<br><br>Environment Type: Environment variables are often used **to store the name of the environment in which the app is currently running**. The app's logic can use this value to access the right set of resources or enable/disable certain features or sections of the app.<br><br>- Can use for any app running on OS<br>- for configurations<br>- Internationalization, localisation, security<br>- config paths etc                                                                                                       |
| What is the data type <br>of the environment variable                            | String                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| How many environment <br>would get  by a <br>java app                            | Two Environments<br><br>1.Os Environment<br>2.Java Environment<br><br>![[Pasted image 20240401120520.png]]<br><br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| What is the syntax <br>of environment varialbe                                   | KEY=VALUE<br><br>Not allowed to use spaces.<br>If it is required to put spaces in to the value " " can be used<br>KEY="VALUE"                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| What is the naming convention<br>of key                                          | Upper Case + Snake case                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| How to add a <br>environment Variable in unix like<br>system                     | ![[Pasted image 20240401114634.png]]<br>These files can be used to create the environment variable<br><br>After change the file use this code<br>source [file name]<br>if there is no error occurred. Then it is ok. Otherwise have to change the again.<br><br>open a file using a edito (gedit or nano)<br>![[Pasted image 20240401115348.png]]<br><br>then create the environment variable like this<br>![[Pasted image 20240401115613.png]]<br><br>Now check is there any error using source.[file name]<br>![[Pasted image 20240401122045.png]]<br>This is worked correctly with .profile |
| What are the files<br>that can be used to set the OS environment<br>variable     | .bashrc<br>.zsrhc<br>.profile<br>(These are hidden files, that why . is being used)<br><br>![[Pasted image 20240401121856.png]]<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Is it allowed to change the value <br>of the  OS environment<br>variable in java | No. It is only allowed to read the value of the OS environment variable in java<br><br>It is not allowed to create, change or delete environment variable                                                                                                                                                                                                                                                                                                                                                                                                                                      |


==This could be a interview question==
Question : What is the use of System.getenv( ) method
Answer : To access the OS Environment Variable

How to access to the environment variable when the name is known
```
public class AppInitializer {  
    public static void main(String[] args) {  
          
        //When name of the environment is known  
        String username = System.getenv("USERNAME");  
        System.out.println(username);//ayeshmantha  
  
        String home = System.getenv("HOME");  
        System.out.println(home);///home/ayeshmantha  
    }  
}
```

How to access to all environment variable in java

```  
Map<String, String> osEnv = System.getenv();  
System.out.println(osEnv.get("HOME"));  
  
for (String key : osEnv.keySet()) {  
    System.out.printf("%s=%s \n",key,osEnv.get(key));  
}
```

|                                                                  |                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Is it allowed to change the JVM environment <br>variable in java | Yes. It is allowed to create , delete,                                                                                                                                                                                                                                                                                                                                                              |
| What is the purpose of using<br>JVM environment                  | To store the data related to the project in string format.<br><br>It is allowed to change and add new environment variable but those are rid off after  closing the application.<br><br>JVM is collected those variables when the JVM is run                                                                                                                                                        |
| how to add new JVM Environment variable                          | java HelloWorld<br><br>java -Didentifier=value -Didentifier=value HelloWorld<br><br>Hello world is a class file here<br><br>-D denoted the add a new environment variable with the given indetifier name                                                                                                                                                                                            |
| Who have the access to these JVM environment variables           | Anyone who use the application. The module, package or anything not a concern for this. <br><br>Even for the difference teams have access for these variables<br><br>Anyone who in the JVM Environment                                                                                                                                                                                              |
| How to set this using <br>intellij idea                          | ![[Pasted image 20240401131207.png]]<br>run -> edit configureation ->add vm option<br><br>![[Pasted image 20240401131339.png]]                                                                                                                                                                                                                                                                      |
| How to set the environment <br>variable using codes              | ![[Pasted image 20240401132345.png]]<br>But when use this method (setProporties) all other variables are collected from the JVM are cleared and newly added variables are available. <br><br>![[Pasted image 20240401132630.png]]<br>When using this method (setProperty) all variables that collected from the JVM and newly added variables are available.                                        |
| Explain the use of these api (methods)                           | System.getEnv( ) -> <br>to get os envrionment variable<br><br>System.getProperty( ) -><br>to get JVM Envronment variable<br><br>System.getProperties( ) -><br>to get all JVM Environment variable<br><br>System.setProperties( ) -><br>to set JVM Environment variables replacing all other JVM Environment variables <br><br>System.setProperty( ) -><br>to set a JVM Environment variable<br><br> |
How to access JVM Environment variable

when the identifier is known ->
```
public class JVMEnv {  
    public static void main(String[] args) {  
        //When the identifier of the name is known   
String homeDirPath = System.getProperty("user.home");  
        System.out.println(homeDirPath);//To get the use  
  
        String javaVersion = System.getProperty("java.version");  
        System.out.println(javaVersion);// To get the java version  
  
        String osArch = System.getProperty("os.arch");  
        System.out.println(osArch);// To get the os architecture  
  
    }  
}
```

How to get the all JVM Environment variable

```
import java.util.Properties;  

public class JVMEnv {  
    public static void main(String[] args) {  
//        //When the identifier of the name is known  
//        String homeDirPath = System.getProperty("user.home");  
//        System.out.println(homeDirPath);//To get the use  
//  
//        String javaVersion = System.getProperty("java.version");  
//        System.out.println(javaVersion);// To get the java version  
//  
//        String osArch = System.getProperty("os.arch");  
//        System.out.println(osArch);// To get the os architecture  
        // To get the all JVM Environment variables        Properties properties = System.getProperties();  
  
        for (Object key : properties.keySet()) {  
            String property = properties.getProperty(key.toString());  
            System.out.printf("%s=%s \n" , key, property);  
        }  
  
    }  
}
```


