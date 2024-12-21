
```java
implements View.OnClickListener
```

```java
public void onClick(View v) {  
    nameview = findViewById(R.id.nameV);  
    getname = findViewById(R.id.edtName);  
    mailview = findViewById(R.id.EmailV);  
    getmail = findViewById(R.id.Email);  
    if(v.getId()==R.id.button){  
        Toast.makeText(this, "Hello", Toast.LENGTH_SHORT).show();  
        nameview.setText("Your Name : "+getname.getText().toString());  
        mailview.setText("Your Email : "+getmail.getText().toString());  
    }  
    //we can also use this for an editable field
    if(v.getId()==R.id.edtName){  
    Toast.makeText(this, "Hello", Toast.LENGTH_SHORT).show();  
  	}
}
```


```java
///Inside oncreate
Button btnHello = findViewById(R.id.button);  
btnHello.setOnClickListener(this);
	//For editabel field
getname = findViewById(R.id.edtName);  
getname.setOnClickListener(this);
```