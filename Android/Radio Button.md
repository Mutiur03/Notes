```java
radio=findViewById(R.id.bal);  
radio.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() {  
    @Override  
    public void onCheckedChanged(RadioGroup group, int checkedId) {  
        if(checkedId==R.id.radio1){  
            Toast.makeText(MainActivity.this, "Single", Toast.LENGTH_SHORT).show();  
        }  
        else if(checkedId==R.id.radio2){  
            Toast.makeText(MainActivity.this, "Married", Toast.LENGTH_SHORT).show();  
        }  
    }  
});
```

And other are same as checked