

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string str="aab";
    string s="aba";
    str+=str;
    cout<<(str.find(s)!=string::npos );
}
```