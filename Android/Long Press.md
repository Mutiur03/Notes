
```java
nameview = findViewById(R.id.nameV);  
nameview.setOnLongClickListener((v1 -> {  
    nameview.setText("");  
    return true;  
}));
```

**OR**

```java
nameview = findViewById(R.id.nameV);  
nameview.setOnLongClickListener(new View.OnLongClickListener()  {  
    @Override  
    public boolean onLongClick(View v) {  
        nameview.setText("");  
        return true;  
    }  
});
```