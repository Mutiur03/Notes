Basic Syntax
```java
public class File_Name {  
    public static void main(String[] args){  
        System.out.print("Hello"); 
    }  
}
```
To print anything without newline use
```java
System.out.print("Hello");
```
with new line
```java
System.out.println("Hello");
```

For taking user input
```java
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);  
        System.out.println("Enter your name: ");  
        String name;  
        name=a.nextLine();  //for string
        System.out.println(a);  
  
    }  
}
```
```java
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);  
        System.out.println("Enter your age: ");  
        int b=a.nextInt();  //for int
        System.out.println(b);  
    }  
}
```
according to the input type we have to select function for Scanner class.

When we take input of string after int then we get empty string and can't get any chance to enter any string. the main reason for this is that when we enter any int then press enter then nextInt() capture the int but \n stays there and input string take that \n as an input and that's why we don't get any chance to enter anything as input.

So the wrong process is 
```java
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);  
        System.out.println("Enter your age: ");  
        int b=a.nextInt();   
        System.out.println("Enter Your name");  
        String c=a.nextLine();  
        System.out.println("Your name :"+ c);  
        System.out.println("Your Age :"+ b);  
    }  
}
```

Correct Process
```java
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);  
        System.out.println("Enter your age: ");  
        int b=a.nextInt();  
        a.nextLine();  //This is the differenece
        System.out.println("Enter Your name");  
        String c=a.nextLine();  
        System.out.println("Your name :"+ c);  
        System.out.println("Your Age :"+ b);  
    }  
}
```


To take only the first word from string then we use next()

```java
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);   
        String m=a.next();;  
        System.out.println("Your Name?");  
        System.out.println("My first name is "+m);  
    }  
}
```

Generate random number
```java
import java.util.Random;  
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Random rand=new Random();  
        int a= rand.nextInt(20);  //20 for limit of highest limit
        //if we use n then we will get 0 to n-1. To get 1 to n we have to use
        // rand.nextInt(n)+1 
        System.out.println(a);  
    }  
}
```


Creating a game using random number.
```java
import java.util.Random;  
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner a=new Scanner(System.in);  
        System.out.println("**Guess the number**");  
        System.out.print("Enter your name ");  
        String name=a.nextLine();  
        System.out.println("Welcome "+name);  
        System.out.print("Enter your limit ");  
        int l=a.nextInt();  
        Random random=new Random();  
        int r= random.nextInt(l)+1;  
        int g;  
        int c=0;  
        System.out.println("Enter a number within the limit");  
        while (true){  
            g=a.nextInt();  
            c++;  
            if(g==r){  
                System.out.println("Congratuations");  
                System.out.println("You have took "+c+" try.");  
                break;  
            }  
            else System.out.println("Try Again");  
        }  
  
    }  
}
```

**Project using concepts of OOP**
```java
//Main function
import java.util.Arrays;  
import java.util.Scanner;  
public class HelloWorld {  
    public static void main(String[] args){  
        Scanner scanner=new Scanner(System.in);  
        input i=new input();  
        System.out.println("Name : Mutiur");  
        System.out.println("Age : 21");  
        int c;  
        while(true){  
            i.execute();  
            c=scanner.nextInt();  
            if(c==6){  
                break;  
            }  
            else {  
                i.in(c);  
            }  
        }  
        }  
}
```
```java
//Input Class
import java.util.Scanner;  
public class input {  
    public input(){  
    }  
    Scanner scanner=new Scanner(System.in);  
    public void execute(){  
        System.out.println("Choose your organ:");  
        System.out.println("\t1. Left Eye");  
        System.out.println("\t2. Right Eye");  
        System.out.println("\t3. Heart");  
        System.out.println("\t4. Stomach");  
        System.out.println("\t5. Skin");  
        System.out.println("\t6. Quit");  
    }  
    Eye l=new Eye("Left Eye", "Short sighted", "Blue");  
    Eye r=new Eye("Right Eye", "Normal", "Blue");  
    Heart h=new Heart("Heart", "Short sighted", 65);  
    public void in(int c){  
        switch (c){  
            case 1:{  
                l.r();  
                l.check();  
                int in=scanner.nextInt();  
                if(in==1) l.setb();  
                break;  
            }  
            case 2:{  
                r.r();  
                r.check();  
                int in=scanner.nextInt();  
                if(in==1) r.setb();  
                break;  
            }  
            case 3:{  
                h.r();  
                int in=scanner.nextInt();  
                if(in==1) {System.out.print("Enter the new heart rate :");  
                int r=scanner.nextInt();  
                h.setRate(r);}  
                break;  
            }  
            case 4:{  
  
            }  
            case 5:{  
  
            }  
            default: {  
                System.out.println("Wrong Input");  
            }  
        }  
    }  
}
```
```java
//Organ Class
public class Organ {  
    String name;  
    String condition;  
    public Organ(String name, String condition) {  
    this.name=name;  
    this.condition=condition;  
    }  
    public void r(){  
        System.out.println("Name: "+name);  
        System.out.println("Medical Condition :"+condition);  
    }  
}
```
```java
//Eye Class
public class Eye extends Organ {  
        String color;  
        boolean open=true;  
        public Eye(String name, String condition, String color) {  
            super(name,condition);  
            this.color=color;  
        }  
        @Override  
        public void r() {  
            super.r();  
            System.out.println("Color :"+color);  
        }  
        public void check(){  
            if(open)  
                System.out.println("\t1. Close your eye");  
            else {  
                System.out.println("\t1. Open your eye");  
            }  
        }  
        public void setb(){  
            if(open){  
                System.out.println(this.name+" eye closed");  
            }  
            else {  
                System.out.println(this.name+" eye opend");  
            }  
            open= !open;  
        }  
  
    }
```
```java
//Heart Class
public class Heart extends Organ{  
    int rate;  
    public Heart(String name, String condition, int rate) {  
        super(name, condition);  
        this.rate = rate;  
    }  
    @Override  
    public void r() {  
        super.r();  
        System.out.println("Heart rate is :"+rate);  
        System.out.println("\t1. Change the heart rate");  
    }  
    public void setRate(int rate){  
        this.rate=rate;  
        System.out.println("Heart rate changed to "+rate);  
    }  
}
```

