##### Initialization
```java
ArrayList<DataType> roll=new ArrayList<>();
```
##### Taking Input
```java
String t;  
System.out.println("Enter your roll :");  
    t=scanner.nextLine();  
    roll.add(t); 
```
##### Print any specific index
```java
System.out.println(roll.get(index));
```
##### Print whole array
```java
System.out.println(VarName);
```
```java
ArrayList<Integer> arr= new ArrayList<>();  
arr.add(25);  
arr.add(26);  
arr.add(28);  
arr.add(56);  
arr.add(28);  
for(Integer s: arr){  
    System.out.println(s);  
}
```
##### Clear
```java
System.out.println(roll.size());
```
##### Remove Element
```java
System.out.println("Enter roll you want to remove :");  
String in=scanner.nextLine();  
roll.remove(in);
```
##### Checking if empty
```java
System.out.println(roll.isEmpty());
```
##### Get index of any element
```java
String  i= scanner.nextLine();  
System.out.println(roll.indexOf(i));
```
##### Sort and Reverse
```java
Collections.sort(VarName);  
Collections.reverse(VarName);
```
### Uses in OOP
```java
//Main Function
import java.util.*;  
public class Main {  
    public static void main(String[] args) {  
        Scanner scanner=new Scanner(System.in);  
        ArrayList<Students> s= new ArrayList<>();  
        s.add(new Students("Mutiur", 2207097));  
        s.add(new Students("Kanchi",2299001));  
        for (Students students:s){  
            System.out.print(students.getName());  
            System.out.print(students.getRoll());  
            System.out.println();  
        }  
    }  
}
```
```java
//Students class
public class Students {  
    String name;  
    int roll;  
  
    public Students(String name, int roll) {  
        this.name = name;  
        this.roll = roll;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public int getRoll() {  
        return roll;  
    }  
}
```