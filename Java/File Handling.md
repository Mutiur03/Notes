
```java
import java.io.File;  
  
public class Main {  
    public static void main(String[] args) {  
        File file=new File("D:/Java/File Handling/src/text.txt");  
        if(file.exists()){  //Won't create a file automatically
            System.out.println("File is available");  
            System.out.println(file.getPath());  
            System.out.println(file.getAbsolutePath());  
            //file.delete();  
        }  
        else System.out.println("File is not available");  
  
    }  
}
```

Writing (will create a file automatically)
```java
import java.io.FileWriter;  
import java.io.IOException;  
  
public class Main {  
    public static void main(String[] args) throws IOException {  
    try {  
        FileWriter fileWriter = new FileWriter("text.txt", true); 
        //To append, the  append part will be true. Otherwise it will only write
        fileWriter.write("Mutiur Rahman\n");  
        fileWriter.close();  
    } catch (IOException e) {  
        throw new RuntimeException(e);  
    }  
} 
}
```

Reading
```java
public class Main {  
    public static void main(String[] args) throws IOException {  
        try (BufferedReader reader = new BufferedReader(new FileReader("text.txt"))) {  
            String line;  
            while ((line = reader.readLine()) != null) {  
                System.out.println(line);  
            }  
        } catch (IOException e) {  
            System.err.println("An error occurred while reading the file: " + e.getMessage());  
        }  
    }  
}
```