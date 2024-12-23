IO - Input / Output

|                                                              |                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What are the main <br>two parts of IO                        | File I/O -> File related input / Output <br><br>Network I /O -> Network Related Input / Output                                                                                                                                                                                                                                                         |
| What are the packages <br>for input output in base<br>module | java.io.*<br>java.nio.* (new input out put)<br>java.net.*                                                                                                                                                                                                                                                                                              |
| What is the difference <br>between java.io and <br>java.nio  | java.io is the older one and java.nio is introduced later since java 7<br><br>There is no performance difference between java.io and java.nio<br><br>==The I/O operations in java.io are mostly blocking. java.<br>java.nio supports both blocking and non blocking.==<br><br>due to this reason some time java.nio is being called as non blocking io |
| Is java.nio is a replacement<br>of a java.io                 | No it is not a replacement for the java.io<br><br>both java io and nio are needed for the development                                                                                                                                                                                                                                                  |

==How to get the partition list==
```
import java.io.File;  
import java.nio.file.FileSystem;  
import java.nio.file.FileSystems;  
import java.nio.file.Path;  
  
public class Demo1 {  
    public static void main(String[] args) {  
        //If we execute this in windows, then we should get the  
        //partition list like C, D, E etc             
	    // Using io  
        File[] roots = File.listRoots();  
        for (File root : roots) {  
            System.out.println(root);  
        }  
  
        // Using nio  
        for (Path rootDirectory : FileSystems.getDefault().getRootDirectories()) {  
            System.out.println(rootDirectory);  
        }  
    }  
      
}
```


|                                                                              |                                                                                                                                                                                                                                                        |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| What is the syntax of the path                                               | ![[Pasted image 20240401141338.png]]<br><br>File separator can be changed with the OS. In window it can be used both "forward slash" and  " backward shlash "<br>But in unix based Os the file separator is the  forward slash                         |
| ==What is the difference between<br>file separator  and <br>path separator== | Path separator is used to separate the several paths.<br><br>File separator is used to separate the files and directory <br>when define a path<br><br>in windows the path separator is -> ; (semi-colon)<br>In Unix-like path separator is ->: (colon) |

==How to get the file separator of the OS==
Interview question
```
import java.io.File;  
import java.nio.file.FileSystems;  
  
public class Demo2 {  
    public static void main(String[] args) {  
        //File separator C:\Windows\temp  
  
        String fileSeparator = System.getProperty("file.separator");  
        System.out.println(fileSeparator);  
  
        System.out.println(File.separator);  
        System.out.println(File.separatorChar);  
  
        System.out.println(FileSystems.getDefault().getSeparator());  
    }  
}
```

==How to get the path separator of the OS==

```
import java.io.File;  
  
public class Demo3 {  
    public static void main(String[] args) {  
        //via Env API  
        String pathSeparator = System.getProperty("path.separator");  
        System.out.println(pathSeparator);  
  
        //Via IO API  
        System.out.println(File.pathSeparator);  
        System.out.println(File.pathSeparatorChar);  
  
    }  
}
```


|                                     |                                                           |
| ----------------------------------- | --------------------------------------------------------- |
| how to create a <br>file using java | 1.First set a point using file (io) or path (nio)<br><br> |

==How to point in a directory== (This is only works with ubuntu)

```
import java.io.File;  
import java.nio.file.Files;  
import java.nio.file.Path;  
import java.nio.file.Paths;  
  
public class PointingDemo {  
    public static void main(String[] args) {  
  
        //Using io  
        File desktopPath1 = new File("/home/ayeshmantha/Desktop/");
        //In here file is refer to a path. Not a file  
        System.out.println(desktopPath1.exists());  
          
        //Using nio  
        Path desktopPath2 = Paths.get("/home/ayeshmantha/Desktop/");  
        System.out.println(Files.exists(desktopPath2));  
    }  
}
```


|                                                          |                                                                                                |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| Why the above code<br>is not the best way set<br>a point | It is not a best way to hard code like above. Because it <br>it won't works with difference OS |

==How to fix above case without doing hard code==

```
import java.io.File;  
import java.nio.file.Files;  
import java.nio.file.Path;  
import java.nio.file.Paths;  
  
public class PointingDemo2 {  
    public static void main(String[] args) {  
        System.out.println(System.getenv("HOME"));  
        System.out.println(System.getenv("user.home"));  
  
        File homeDir1 = new File(System.getenv("HOME"));  
        System.out.println(homeDir1.exists());  
  
        Path homeDir2 = Paths.get(System.getProperty("user.home"));  
        System.out.println(Files.exists(homeDir2));  
  
        File desktopDir1 = new File(System.getenv("HOME") + "/Desktop");  
        //This might not work with other OS  
        File desktopDir2 = new File(System.getenv("HOME") + File.separator + "Desktop");  
  
    }  
}
```

Also this way not give a best readability. 

==How to enhance the readability==
```
import java.io.File;  
import java.nio.file.Files;  
import java.nio.file.Path;  
import java.nio.file.Paths;  
  
public class PointingDemo2 {  
    public static void main(String[] args) {  
        System.out.println(System.getenv("HOME"));  
        System.out.println(System.getenv("user.home"));  
  
        File homeDir1 = new File(System.getenv("HOME"));  
        System.out.println(homeDir1.exists());  
  
        Path homeDir2 = Paths.get(System.getProperty("user.home"));  
        System.out.println(Files.exists(homeDir2));  
  
        File desktopDir1 = new File(System.getenv("HOME") + "/Desktop");  
        //This might not work with other OS  
        File desktopDir2 = new File(System.getenv("HOME") + File.separator + "Desktop");  
  
        File desktopDir3 = new File(System.getenv("HOME") , "Desktop");  
  
    }  
}
```

replace above code with github. Because in here it is not used Path.

|                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ==What is the difference between<br>creating a point using  File ( java.io) and<br>Path (java.nio)== | "File" only allow to set two directory but "Path" doesn't have that kind of restraint.                                                                                                                                                                                                                                                                            |
| What are the constructors <br>in File( ). Explain the difference                                     | 1) new File (String path) -><br>using string path<br>`new File("/home/ayeshmantha/Desktop/");`<br><br>2)new File(String parent, String child)-><br>using string parent and string child<br>`new File(System.getenv("HOME") , "Desktop");`<br><br>3) new File(File parent, String child)-><br>using file parent and string child<br>`new File(desktopDir, "abc");` |

![[Pasted image 20240401145912.png]]

Do example demo 3, demo 4, 

|                                                         |     |
| ------------------------------------------------------- | --- |
| [[Creating directory and files]]                        |     |
| [[how to move, rename folder,files]]                    |     |
| [[how to copy files,folders]]                           |     |
| [[how to list files]]                                   |     |
| [[What is the difference between java.io and java.nio]] |     |
