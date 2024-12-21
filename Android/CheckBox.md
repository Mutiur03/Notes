```java
checkBox1=findViewById(R.id.checkbox1);  
checkBox2=findViewById(R.id.checkbox2);  
checkBox1.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {  
    @Override  
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {  
        if(isChecked){  
            isChecked=false;  
            Toast.makeText(MainActivity.this,"Do it fast",Toast.LENGTH_LONG).show();  
        }  
        else isChecked=true;  
    }  
});
```

To cut line in the middle when checked
```java
checkBox1=findViewById(R.id.checkbox1);  
checkBox1.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {  
    @Override  
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {  
        if(isChecked){  
            checkBox1.setPaintFlags(checkBox1.getPaintFlags() | Paint.STRIKE_THRU_TEXT_FLAG);  
        }  
        else {  
            checkBox1.setPaintFlags(checkBox1.getPaintFlags() & (~Paint.STRIKE_THRU_TEXT_FLAG));  
            //Or we can use
            checkBox1.setPaintFlags(0);
        }  
    }  
});
```


Other actions we can do

- **`Paint.UNDERLINE_TEXT_FLAG`**: Underlines the text.
- **`Paint.STRIKE_THRU_TEXT_FLAG`**: Adds a strikethrough line on the text.
- **`Paint.FAKE_BOLD_TEXT_FLAG`**: Makes text appear bold (not the same as setting bold style in fonts).
- **`Paint.ANTI_ALIAS_FLAG`**: Smoothens edges for better rendering

Remove that line
```java
layout=findViewById(R.id.frame);  
checkBox1.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {  
    @Override  
    public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {  
        if(isChecked){    
            checkBox1.setText("");  
            if(checkBox1.getText()==""){  
                    layout.removeView(checkBox1);  
            }  
        }  
    }  
});
```