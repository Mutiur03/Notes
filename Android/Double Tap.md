
```java
GestureDetector gestureDetector=new GestureDetector(this,new GestureDetector.SimpleOnGestureListener() {  
    @Override  
    public boolean onDoubleTap(@NonNull MotionEvent e) {  
        nameview.setText("");  
        return true;  
    }  
});
nameview.setOnTouchListener((v, event) -> gestureDetector.onTouchEvent(event));
```

