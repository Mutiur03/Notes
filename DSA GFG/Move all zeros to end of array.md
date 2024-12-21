#### Naive Approach

Using Temp array ***(first copy non zero element then insert 0 as needed.)***
**Time** 
**O(n)**
Space O(n)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    vector<int>t;
    for(int i=0; i<v.size(); i++){
        if(v[i]!=0) t.push_back(v[i]);
    }
    while(t.size()<v.size()){
        t.push_back(0);
    }
    for(int c:t){
        cout<<c<<" ";
    }
}
```
#### Better Approach

Two Traversals (***If the element is non zero then we will shift that element to the index of previous zero***)
Time 
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    int c=0;
    int i;
    for(i=0; i<v.size(); i++){
        if(v[i]!=0) {
            v[c]=v[i];
            c++;
        }
    }
    while(c<i){
        v[c]=0;
        c++;
    }
    for(int g:v){
        cout<<g<<" ";
    }
}
```

## **Expected Approach**

One Traversal(***It's like the previous one but difference is that here we will use one loop and swap the value of zero element index and another non zero***)
Time
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    int c=0;
    int i;
    for(i=0; i<v.size(); i++){
        if(v[i]!=0) {
            swap(v[c],v[i]);
            c++;
        }
    }
    for(int g:v){
        cout<<g<<" ";
    }
}
```

## **In-Built Library**

In C++, there exists a method [stable_parition()](https://www.geeksforgeeks.org/stdstable_partition-in-c/) that we can directly use here to implement the above method.
Time
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
void pushZerosToEnd(vector<int> &arr) {
    stable_partition(arr.begin(), arr.end(), [](int n) {
                                        return n != 0; });
}
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    pushZerosToEnd(v);
    for(int g:v){
        cout<<g<<" ";
    }
}
```