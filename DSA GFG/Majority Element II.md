#### Naive
Mayre cdi


### Expected

Using HashMap
Time 
**O(n)**
Space O(n)

```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int>v={1,2,1,1,2,1,2,2,1,1,2,3,5,2,2,1,3,4,5,5};
    map<int,int>m;
    for(auto c:v){
        m[c]++;
    }
    int n=v.size()/3;
    v.clear();
    for(auto c:m){
        if(c.second>n){
            v.push_back(c.first);
        }
    }
    for(auto g:v){
        cout<<g<<" ";
    }
}
```

## **Boyer-Moore’s Voting Algorithm** 
(হজম হয়নি)

According to the algo max two element can pass that condition. So we will count that two element.
Time 
**O(n)**
Space O(1)

```cpp
#include<bits/stdc++.h>
using namespace std;
vector<int> findMajority(vector<int> &arr) {
    int n = arr.size();
    int ele1 = -1, ele2 = -1, cnt1 = 0, cnt2 = 0;
    for (int ele : arr) {
        if (ele1 == ele) {
            cnt1++;
        }
        else if (ele2 == ele) {
            cnt2++;
        }
        else if (cnt1 == 0) {
            ele1 = ele;
            cnt1++;
        }
        else if (cnt2 == 0) {
            ele2 = ele;
            cnt2++;
        }
        else {
            cnt1--;
            cnt2--;
        }
    }
    vector<int> res;
    cnt1 = 0;
    cnt2 = 0;
    for (int ele : arr) {
        if (ele1 == ele) cnt1++;
        if (ele2 == ele) cnt2++;
    }
    if (cnt1 > n / 3) res.push_back(ele1);
    if (cnt2 > n / 3 && ele1 != ele2) res.push_back(ele2);
    if(res.size() == 2 && res[0] > res[1])
        swap(res[0], res[1]);
    return res;
}
int main() {
    vector<int> arr = {2, 2, 3, 1, 3, 2, 1, 1};
    vector<int> res = findMajority(arr);
    for (int ele : res) {
        cout << ele << " ";
    }
    return 0;
}
```