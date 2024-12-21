****Time Complexity****: O(n)  
****Space:**** O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string str="anngram";
    string s;
    s="annagram";
    int n=str.length();
    map<char,int>m;
    for(auto c:str){
        m[c]++;
    }
    for(auto c:s){
        m[c]--;
    }
    for(auto p:m){
        if(p.second!=0) {
        cout<<"NOT annagram"<<endl;
        return 0;}
    }
    cout<<"annagram"<<endl;
}
```