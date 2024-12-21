This keyword used for fixed value or function. Like we want any variable Value same for all object of that class then we use static keyword. We can access that variable without initiating any object... Also same for static function.

```java
//Main
public class Main {  
    public static void main(String[] args) {  
        Students.setName("Mutiur");  
        // Here we can see that we can access name var without any object.  
        System.out.println(Students.getName());  
        Students.print();  
        // Also can access static func without object.  
    }  
}
```
```java
//Students Class
public class Students {  
    static String name;  
    int roll;  
    String Dept;  
    int year;  
  
    public Students(int roll, String dept, int year) {  
        this.roll = roll;  
        Dept = dept;  
        this.year = year;  
        // Here we can see that there is no way to edit name var using constructor.  
    }  
  
    public static String getName() {  
        return name;  
    }  
  
    public static void setName(String name) {  
        Students.name = name;  
        // This is the only way to initialize name var.  
    }  
  
    public int getRoll() {  
        return roll;  
    }  
  
    public void setRoll(int roll) {  
        this.roll = roll;  
    }  
  
    public String getDept() {  
        return Dept;  
    }  
  
    public void setDept(String dept) {  
        Dept = dept;  
    }  
  
    public int getYear() {  
        return year;  
    }  
  
    public void setYear(int year) {  
        this.year = year;  
    }  
    public static void print(){  
        System.out.println("Printing...");  
        // This is static function.  
    }  
}
```