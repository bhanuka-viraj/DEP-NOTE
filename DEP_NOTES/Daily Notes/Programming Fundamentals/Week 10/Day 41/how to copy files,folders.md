
|                                                                  |                                                                                                 |
| ---------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| how  to copy<br>file and folders in<br>java.io                   | There is no direct way to do copy and file in java.io                                           |
| How to copy file and <br>folder using java.nio                   | using copy( ) api                                                                               |
| Is it allowed to<br>copy folders with content using java.ion<br> | No. There is no direct way copy a folder with the content using a api. Just copy a empty folder |
| How to replace a file<br>when copy                               | ![[Pasted image 20240401184421.png]]<br><br>using this "StandardCopyOption.Replace_Existing"    |
| Is it allowed to copy <br>files using java.nio                   | yes. But only one file can be copied once                                                       |
| How to copy a folder with content using <br>java.io              | There is n                                                                                      |

How to copy folders with the content
(only files are copied as content. Folders are copied but without the content)

using java.nio ->
```
import java.io.IOException;  
import java.nio.file.Files;  
import java.nio.file.Path;  
import java.nio.file.Paths;  
  
public class OperationDemo15 {  
    public static void main(String[] args) throws IOException {  
        Path source = Paths.get(System.getenv("HOME"), "Desktop", "icons");  
        Path target = Paths.get(System.getenv("HOME"), "Downloads" ,"icons");  
  
        Files.copy(source, target);  
  
        for (Path path : Files.newDirectoryStream(source)) {  
            Files.copy(path, target.resolve(path.getFileName()));  
        }  
  
    }  
}

```


