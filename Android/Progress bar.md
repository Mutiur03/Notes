
To show for any condition
```java
radio=findViewById(R.id.bal);  
radio.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() {  
    @Override  
    public void onCheckedChanged(RadioGroup group, int checkedId) {  
        if(checkedId==R.id.radio1){    
            progressBar.setVisibility(View.VISIBLE);  
        }  
        else if(checkedId==R.id.radio2){    
            progressBar.setVisibility(View.GONE);  
        }  
    }  
});  
progressBar=findViewById(R.id.progressBar);
```

To show incresing
```java
progressBar=findViewById(R.id.progressBar);  
Thread thread=new Thread(new Runnable() {  
    @Override  
    public void run() {  
        for(int i=0; i<100; i++){  
            progressBar.incrementProgressBy(1);  
            SystemClock.sleep(500);  
        }  
    }  
});  
thread.start();
```