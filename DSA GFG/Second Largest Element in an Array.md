#### Naive Approach

Using sorting
**Time** 
**O(n * logn)**
Space O(1)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){

    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};

    sort(v.begin(),v.end());

    int sl;

    for(int i=v.size()-2; i>=0; i--){

        if(v[i]!=v[i+1]){

            sl=v[i];

            break;

        }

    }

    cout<<sl;

}
```


#### Better Approach

Two Pass Search (***In first step we will find largest one then we have to find second one, using two for loop***)
Time 
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){

    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};

    sort(v.begin(),v.end());

    int sl=-1,l=-1;

    for(int i=0; i<v.size(); i++){

        if(v[i]>l) l=v[i];

    }

    for(int i=0; i<v.size(); i++){

        if(v[i]!=l && v[i]>sl) sl=v[i];

    }

    cout<<sl;

}
```

## **Expected Approach**

One Pass Search(***in this step we will find largest and second largest, using one for loop***)
Time
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>

using namespace std;

int main(){

    vector<int>v={1,2,0,5,1,0,6,0,4,0,5};

    sort(v.begin(),v.end());

    int sl=-1,l=-1;

    for(int i=0; i<v.size(); i++){

        if(v[i]>l){

            sl=l;

            l=v[i];

        }

        else if(v[i]<l && v[i]>sl){

            sl=v[i];

        }

    }

    cout<<sl;

}
```