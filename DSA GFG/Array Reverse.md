#### Naive Approach

Using Temp Array
Time
**O(n)**
Space O(n)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    vector<int>temp;
    for(int i=v.size()-1; i>=0; i--)
        temp.push_back(v[i]);
    for(int g:temp){
        cout<<g<<" ";
    }
}
```


#### Expected - 01

Using Two Pointer
Time 
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};
    int l=0, r=v.size()-1;
    while(l<r){
        swap(v[l],v[r]);
        l++,r--;
    }
    for(int g:v){
        cout<<g<<" ";
    }
}
```


#### Expected - 02 (Also Naive)

Using swapping element ***(Using two index)***
Time 
**O(n)**
Space O(1)

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5};
    for (int i = v.size() - 1, j = 0; j < v.size() / 2; i--, j++)
        swap(v[i], v[j]);
    for (int g : v)
    {
        cout << g << " ";
    }

}
```

#### Alternate

Using recursion
Time 
**O(n)**
Space O(n)

```cpp
#include <bits/stdc++.h>
using namespace std;
void rev(vector<int> &v, int l, int r)
{
    if (l >= r)
        return;
    swap(v[l], v[r]);
    rev(v, l + 1, r - 1);
}
int main()
{
    vector<int> v = {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5};
    rev(v, 0, v.size() - 1);
    for (int g : v)
    {
        cout << g << " ";
    }
}
```

#### In-Built

Time
**O(n)**
Space O(n)

```cpp
reverse(v.begin(),v.end());
```