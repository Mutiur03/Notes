
We can use toString() to define output of a class
```java
public class Main {  
    public static void main(String[] args) {  
        car c=new car();  
        System.out.println(c);  
    }  
}
```
```java
public class car{  
    String  name="Shit";  
    String model="VS465";  
    int relese=2021;  
    public String toString(){  
        return name+"\n"+model+"\n"+relese;  
    }  
}
```

Passing object as parameter

```java
public class Main {  
    public static void main(String[] args) {  
        Garage garage=new Garage();  
        car cc= new car();  
        garage.checkin(cc);  
    }  
}
```
```java
public class car{  
    String  name="Shit";  
    String model="VS465";  
    int relese=2021;  
    public String toString(){  
        return name+"\n"+model+"\n"+relese;  
    }  
}
```
```java
public class Garage {  
    void checkin(car c){  
        System.out.println(c);  
    }  
}
```

![[Pasted image 20241222145130.png]]

