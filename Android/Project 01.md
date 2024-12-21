
```java
public void onClick(View v) {  
  
    String s= editText.getText().toString();  
    if(!s.isEmpty()){  
        CheckBox checkBox=new CheckBox(MainActivity.this);  
        checkBox.setText(s);  
        checkBox.setTextSize(20);  
        checkBox.setLayoutParams(new LinearLayout.LayoutParams(  
                LinearLayout.LayoutParams.MATCH_PARENT,  
                LinearLayout.LayoutParams.WRAP_CONTENT  
        ));  
        linearLayout1.addView(checkBox);  
        editText.setText("");  
        checkBox.setOnCheckedChangeListener((buttonView, isChecked) -> {  
            linearLayout1.removeView(checkBox);  
            linearLayout2.removeView(checkBox);  
            if(isChecked){  
                linearLayout2.addView(checkBox);  
                textView.setVisibility(View.VISIBLE);  
                checkBox.setPaintFlags(checkBox.getPaintFlags() | Paint.STRIKE_THRU_TEXT_FLAG);  
            }  
            else {  
                if(hasCheckBox(linearLayout2)){  
                    textView.setVisibility(View.INVISIBLE);  
                }  
                linearLayout1.addView(checkBox);  
                checkBox.setPaintFlags(0);  
            }  
        });  
    }  
    else {  
        Toast.makeText(MainActivity.this,"Please Enter Task",Toast.LENGTH_SHORT).show();  
    }  
  
}  
public boolean hasCheckBox(LinearLayout linearLayout) {  
    for (int i = 0; i < linearLayout.getChildCount(); i++) {  
        View child = linearLayout.getChildAt(i);  
        if (child instanceof CheckBox) {  
            return false;  
        }  
    }  
    return true;  
}
```