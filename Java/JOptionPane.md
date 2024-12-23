
```java
import javax.swing.JOptionPane;  
public class Main {  
    public static void main(String[] args) {  
        String s=JOptionPane.showInputDialog("Enter your name");  
        if(s==null) System.exit(0);  
        JOptionPane.showMessageDialog(null,"Hello MF "+s);  
        boolean valid=false;  
        int a =0;  
        while(!valid){  
            String in=JOptionPane.showInputDialog("Enter your age");  
            if(in==null) System.exit(0);  
            try{  
                a=Integer.parseInt(in);  
                valid=true;  
            } catch (NumberFormatException e) {  
                // To catch any kind of exception use (Exception e)  
                JOptionPane.showMessageDialog(null,"Wrong age. Try again");  
            }  
        }  
        JOptionPane.showMessageDialog(null,"Your age is "+a);  
    }  
}
```