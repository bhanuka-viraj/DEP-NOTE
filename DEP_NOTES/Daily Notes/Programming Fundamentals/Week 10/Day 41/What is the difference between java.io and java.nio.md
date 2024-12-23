
|                                                   | java.io                                                             | java.nio                                                     |
| ------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------ |
| Symbolik LInks                                    | java.io doesn't have a api to find the <br>symbolic links(shorcuts) | java.nio have a api to find the <br>symbolic links(shorcuts) |
| Perfomance                                        | There is no performance <br>difference                              | There is no performance <br>difference                       |
| How to point <br>in a directory                   | using newFile(directory)<br>                                        | Paths.get(directory)<br>Path.of(directory)                   |
| What is the <br>restraints in<br>creating a point | Allow to set two path elements                                      | No such restraints                                           |
| arising exceptions                                | Rarely arise exceptions                                             | Commonly arise excepitons                                    |
| API to<br>Create a directory<br>without parent    | makdirs( )                                                          | createDirectories( )                                         |
| API to move a <br>folder / file                   | reNameTo( )                                                         | move( )                                                      |
| API to copy                                       | -                                                                   | Files.copy ( )                                               |
| API to list file                                  | listFiles ( )                                                       | Files.newDirectoryStreams( )                                 |
| Blocking ? or<br>Non Blocking?                    | Operations are mostly blocking                                      | Supports both blocking<br>and non-blocking                   |
| API to delete <br>file or folder<br>              | API to delete file or folder                                        | Files.delete(path)                                           |
