
|                                                                                   | Regular Expression Language                                                                                                                                                                                                 |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| How to run a jar file                                                             | `java -jar <file name>`                                                                                                                                                                                                     |
| Why regex was <br>introudeced                                                     | to identify the values that matched a pattern in a large text<br><br>                                                                                                                                                       |
| Why now regex are<br>commonly used                                                | for validation                                                                                                                                                                                                              |
| What does mean match                                                              | characters to match<br><br>![[Pasted image 20240430050711.png]]<br>ex for matching                                                                                                                                          |
| What does mean<br>Mark                                                            | to state from where matching should start(matching will done only in marked context)<br><br>![[Pasted image 20240430050750.png]]<br>example for marking                                                                     |
| [[Rules for regex]]                                                               | Refer this to see rules for regex                                                                                                                                                                                           |
| write a regex for<br>match the phone<br>numbers                                   | 077-1234567<br>011-7654321<br>+9477-4321321<br><br>`(0\d{2}-\d{7})\|([+]94[1-9]{2}-\d{7})`<br>`(0\|[+]94)[1-9]{2}-\d{7}`                                                                                                    |
| How does the <br>class matcher and <br>pattern are involved<br>with regex in java | pattern -> compile<br>mathcer -> execute<br><br><br>![[Pasted image 20240429181140.png]]<br><br>![[Pasted image 20240430051145.png]]                                                                                        |
| ==What is the difference <br>between `matches()` <br>and `find()` in matcher==    | `matches()` -><br>check whether matches all input text with the regex<br>(it is not required to put ^ in the beginining and # in the end)<br><br>`find()` -><br>check whether the input text contain the relevant regex<br> |
| What are the two types of<br>capturing group                                      | Numbers Group<br>Named Group                                                                                                                                                                                                |
| How does the <br>capture groups are<br>numbered<br>(in number group)              | First numbered the largest group and then numbers other group from left to right<br><br>Number 0 group is always the whole text<br><br>![[Pasted image 20240430051340.png]]                                                 |
How does the numbering works in number groups
```
public class Demo4 {  
    public static void main(String[] args) {  
        String dateTime = "2024-04-29 18:36";  
        //language=RegExp  
        String pattern = "((\\d{4})-(\\d{2})-(\\d{2}))\\s((\\d{2}):(\\d{2}))";  
        System.out.println(dateTime.matches(pattern));  
  
  
        Pattern compilePattern = Pattern.compile(pattern);  
        Matcher matcher = compilePattern.matcher(dateTime);  
        matcher.find();  
        System.out.println(matcher.group(0));  
        System.out.println("Date: "+ matcher.group(1));  
        System.out.println("Year: "+ matcher.group(2));  
        System.out.println("Moth: "+ matcher.group(3));  
        System.out.println("Day: "+ matcher.group(4));  
        System.out.println("Time: "+ matcher.group(5));  
        System.out.println("Hours: "+ matcher.group(6));  
        System.out.println("Minutes: "+ matcher.group(7));  
  
  
    }  
}
```


|                                  |                                                                                           |
| -------------------------------- | ----------------------------------------------------------------------------------------- |
| How does the name<br>group works | The groups are given a identifier in here<br><br>![[Pasted image 20240429190142.png]]<br> |
```
public class Demo4 {  
    public static void main(String[] args) {  
        String dateTime = "2024-04-29 18:36";  
        //language=RegExp  
        String pattern = "(?<date>(\\d{4})-(\\d{2})-(\\d{2}))\\s(?<time>(\\d{2}):(\\d{2}))";  
        System.out.println(dateTime.matches(pattern));  
  
  
        Pattern compilePattern = Pattern.compile(pattern);  
        Matcher matcher = compilePattern.matcher(dateTime);  
        matcher.find();  
        System.out.println(matcher.group(0));  
        System.out.println("Date: "+ matcher.group(1));  
        System.out.println("Date: "+ matcher.group("date"));  
        System.out.println("Year: "+ matcher.group(2));  
        System.out.println("Moth: "+ matcher.group(3));  
        System.out.println("Day: "+ matcher.group(4));  
        System.out.println("Time: "+ matcher.group(5));  
        System.out.println("Time: "+ matcher.group("time"));  
        System.out.println("Hours: "+ matcher.group(6));  
        System.out.println("Minutes: "+ matcher.group(7));  
  
  
    }  
}
```