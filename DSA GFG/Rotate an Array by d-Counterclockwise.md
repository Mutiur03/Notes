
#### Naive

Rotate one by one
Time
**O(n* d)**
Space O(1)

```cpp
#include <bits/stdc++.h>
using namespace std;
void rotate(vector<int>&v,int d){
    for(int j=0; j<d; j++){
    int f=v[0];
    for(int i=0; i<v.size()-1; i++){
        v[i]=v[i+1];
    }
   v[v.size()-1]=f;
    }
}
int main()
{  
    vector<int> v = {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5};
    int d=2;
    rotate(v,d);
    for (int g : v)
    {
        cout << g << " ";
    }
}
```

#### Better

Using Temp Array
Time
**O(n)**
Space O(n)

```cpp
#include <bits/stdc++.h>
using namespace std;
void rotate(vector<int>&v,int d){
    vector<int>temp(v.size());
    for(int i=0; i<v.size()-d;i++){
        temp[i]=v[i+d];
    }
    for(int i=v.size()-d,j=0;i<v.size();j++, i++){
        temp[i]=v[j];
    }
    for(int i=0; i<v.size(); i++){
        v[i]=temp[i];
    }
}
int main()
{  
    vector<int> v = {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5};
    int d=5;
    rotate(v,d);
    for (int g : v)
    {
        cout << g << " ";
    }
}
```

## Expected - 01

Using **Jugling Algo** ***(So for any index i we know that after rotation, the element that will occupy this position is v\[(i + d) % n]***.)
Time
**O(n)**
Space o(1)

```cpp

```

## Expected - 02

Using **Reversal Algo**
- ****Reverse**** the subarray containing the ****first d**** elements of the array.
- ****Reverse**** the subarray containing the ****last (n - d)**** elements of the array.
- Finally, ****reverse all the elements**** of the array.
- {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5}
- {2, 1, 0, 5, 1, 0, 6, 0, 4, 0, 5} //Reversed first 2 element
- {2, 1, 5, 0, 4, 0, 6, 0, 1, 5, 0} //Reversed others element
- Reverse Full
- {0 5 1 0 6 0 4 0 5 1 2}
Time
**O(n)**
Space o(1)

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{  
    vector<int> v = {1, 2, 0, 5, 1, 0, 6, 0, 4, 0, 5};
    int d=2;
    reverse(v.begin(),v.begin()+d);
    reverse(v.begin()+d,v.end());
    reverse(v.begin(),v.end());
    for (int g : v)
    {
        cout << g << " ";
    }
}
```