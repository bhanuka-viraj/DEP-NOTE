
|                                                                                                                            |                                                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What would happen when<br>create a directory using<br>mkdir( ) when there is no<br>parent directory <br>(when use java.io) | When the parents directories are not exist not <br>allowed to create the sub directories using<br>mkdir( ).<br><br>Use mkdirs( ) for this kind of cases<br><br>basic-file-operation / operationDemo4 |
| How to handle above case<br>when use the nio                                                                               | use createDirectories( ) instead cretaeDirectory( )                                                                                                                                                  |


```
import java.io.File;
import java.io.IOException;

public class OperationDemo4 {
    public static void main(String[] args) throws IOException {
        File desktopFolder = new File(System.getenv("HOME"), "Desktop");
        File dep12Folder = new File(new File(new File(desktopFolder, "ijse"), "dep"), "12");

        System.out.println("Desktop exists?: " + desktopFolder.exists());
        System.out.println("dep12 exists?: " + dep12Folder.exists());

        boolean created = dep12Folder.mkdirs();
        if (created){
            System.out.println("Folder created");
        }else{
            System.out.println("Folder already exists");
        }
    }
}
```
