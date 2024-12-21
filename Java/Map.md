##### Initialization
```java
Map<Integer,String> VarName=new HashMap<>();
```
##### Taking Input
```java
m.put(1,"Mutiur");
```
##### Print any specific element
```java
System.out.println(m.get(key));
```
##### Print whole Map
```java
System.out.println(VarName);
```
```java
Map<Integer, String> m= new HashMap<>();  
m.put(1,"Mutiur");  
m.put(2,"Kanchi");  
for(Map.Entry<Integer,String> map:m.entrySet()){  
    System.out.println(map.getKey());  
    System.out.println(map.getValue());  
}
```
##### Clear
```java
m.clear();
```
##### Remove Element
```java
m.remove(key);
```
##### Checking if empty
```java
System.out.println(m.isEmpty());
```
##### Check if any key exists or not
```java
System.out.println(m.containsKey(key));
```
##### Check if any value exists or not
```java
System.out.println(m.containsValue(Value));
```
##### Get all keys
```java
System.out.println(m.keySet());
```
##### Get all values
```java
System.out.println(m.values());
```

## Project
```java
//Main
import java.util.Scanner;  
  
public class Main {  
    public static void show(){  
        System.out.println("Which app do you want to open?");  
        System.out.println("\t1. Contacts");  
        System.out.println("\t2. Messages");  
        System.out.println("\t3. Quit");  
    }  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  
        Contacts contacts = new Contacts();  
        Messages messages = new Messages();  
        while (true) {  
            show();  
            int c = scanner.nextInt();  
            if (c == 3) {  
                System.out.println("Quiting...");  
                break;  
            } else {  
                switch (c) {  
                    case 1: {  
                        while (true) {  
                            contacts.show();  
                            System.out.println("Select");  
                            int in = scanner.nextInt();  
                            if (in == 5) break;  
                            contacts.check(in);  
                        }  
                        break;  
                    }  
                    case 2: {  
                        while (true) {  
                            messages.show();  
                            System.out.println("Select");  
                            int in = scanner.nextInt();  
                            if (in == 3) break;  
                            messages.check(in);  
                        }  
                        break;  
                    }  
                    default:{  
                        System.out.println("Invalid");  
                        break;  
                    }  
                }  
            }  
        }  
  
    }  
}
```

```java
//Contacts
import java.util.HashMap;  
import java.util.Map;  
import java.util.Scanner;  
  
public class Contacts {  
    Map<String, String>number=new HashMap<>();  
    Scanner scanner=new Scanner(System.in);  
    void show(){  
        System.out.println("What you want to do?");  
        System.out.println("\t1. Show all contacts");  
        System.out.println("\t2. Add new contacts");  
        System.out.println("\t3. Search for a contact");  
        System.out.println("\t4. Delete a contact");  
        System.out.println("\t5. Go to previous menu");  
    }  
    void showContacts(){  
        if(number.isEmpty()) {System.out.println("No contact has been saved");  
            return;}  
        for(Map.Entry<String,String>map: number.entrySet()){  
            System.out.println(map.getKey()+" :"+map.getValue());  
        }  
    }  
    void setNumber(String name, String phone){  
        number.put(name,phone);  
    }  
    void search(String name){  
        if(number.containsKey(name)){  
            System.out.print(name + " :");  
            System.out.println(number.get(name));  
        }  
        else System.out.println("Not Found");  
    }  
    void remove(String name){  
        if(number.containsKey(name)) {  
            number.remove(name);  
            System.out.println("Removed");  
        }  
        else System.out.println("Not found this contact to remove");  
    }  
    void check(int c){  
        switch (c){  
            case 1:{  
                showContacts();  
                break;  
            }  
            case 2:{  
                System.out.print("Enter new contact name=");  
                String name=scanner.nextLine();  
                System.out.print("Enter new contact number=");  
                String phone=scanner.nextLine();  
                setNumber(name, phone);  
                break;  
            }  
            case 3:{  
                System.out.println("What you want to search?");  
                String name=scanner.nextLine();  
                System.out.println();  
                search(name);  
                break;  
            }  
            case 4:{  
                System.out.println("Which contact do you want to remove?");  
                String name=scanner.nextLine();  
                System.out.println();  
                remove(name);  
                break;  
            }  
            default:{  
                System.out.println("Invalid Input");  
                break;  
            }  
        }  
    }  
}
```

```java
//Message
import java.util.HashMap;  
import java.util.Map;  
import java.util.Scanner;  
  
public class Messages {  
    Map<String,String>msg= new HashMap<>();  
    Scanner scanner=new Scanner(System.in);  
    void show(){  
        System.out.println("What you want to do?");  
        System.out.println("\t1. See the list of all messages");  
        System.out.println("\t2. Send a new message");  
        System.out.println("\t3. Go to previous menu");  
    }  
    void setMsg(String name, String mg) {  
        msg.put(name,mg);  
    }  
    void see(){  
        if(msg.isEmpty()) {System.out.println("No message has been sent");  
            return;}  
        for(Map.Entry<String,String>map: msg.entrySet()){  
            System.out.println(map.getKey()+" :"+map.getValue());  
        }  
    }  
    void check(int c) {  
        switch (c) {  
            case 1: {  
                see();  
                break;  
            }  
            case 2: {  
                System.out.print("Enter contact name=");  
                String name = scanner.nextLine();  
                System.out.print("Enter message=");  
                String msg = scanner.nextLine();  
                setMsg(name, msg);  
                break;  
            }  
            default: {  
                System.out.println("Invalid Input");  
                break;  
            }  
        }  
    }  
}
```