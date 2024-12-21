
****Time Complexity****: O(n)  
****Space:**** O(26)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s="anagram";
    map<char,int> m;
    for(int i=0; i<s.length(); i++){
        if(m[s[i]]==0){m[s[i]]++;}
        else{m[s[i]]=-1;}
    }
    for(int i=0; i<s.length(); i++){
        if(m[s[i]]>0){
            cout<<s[i]<<" "<<i<<endl;
            return 0;
        }
    }
    cout<<"Not found!"<<endl;
}
```