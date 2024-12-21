
#### Naive

The very basic idea that comes to our mind is that we would first [[Generate all possible permutations]] of a given array and sort them. Once sorted, we locate the current permutation within this list. The next permutation is simply the next arrangement in the sorted order. If the current arrangement is the last in the list then display the first permutation (smallest permutation).
***Note: This approach will work only when there are no duplicated in the input array. Please refer the expected approach to handle duplicates.***

Time 
**O(n!.\*n.\*log(n!))**
Space o(n!)

```cpp
#include <bits/stdc++.h>
using namespace std;
void permutation(vector<vector<int>> &res, vector<int> &v, int inx)
{
    if (inx == v.size())
    {
        res.push_back(v);
        return;
    }
    for (int i = inx; i < v.size(); i++)
    {
        swap(v[i], v[inx]);
        permutation(res, v, inx + 1);
        swap(v[i], v[inx]);
    }
}
vector<int> nextpermutation(vector<int>&v){
    vector<vector<int>> res;
    permutation(res, v, 0);
    sort(res.begin(),res.end());
    for(int i=0; i<res.size(); i++){
        if(i<res.size()-1){
            return res[i+1];
        }
        else return res[0];
    }
}
int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    vector<int>t=nextpermutation(v);
    for(auto c:t){
        cout<<c<<" ";
    }
}
```


### Expected
 - Iterate over the given array from end and find the first index (****pivot****) which doesn't follow property of non-increasing suffix, ****(i.e,  arr\[i] < arr\[i + 1]).****
- If ****pivot**** index does not exist, then the given sequence in the array is the largest as possible. So, reverse the complete array. For example, for \[3, 2, 1], the output would be \[1, 2, 3]
- Otherwise, Iterate the array from the end and find for the ****successor (rightmost greater element)**** of pivot in suffix.
- Swap the ****pivot**** and ****successor****
- Minimize the suffix part by reversing the array from ****pivot + 1**** till ****n.****

Time
**O(n)**
Space O(1)

```cpp
#include <bits/stdc++.h>
using namespace std;
vector<int> nextpermutation(vector<int>&v){
    vector<int>r=v;
    int p=-1;
    for(int i=r.size()-2; i>=0; i--){
        if(r[i]<r[i+1]) {p=i;
        break;}
    }
    if(p==-1){
        sort(r.begin(),r.end());
        return r;
    }
    for(int i=r.size()-1; i>p; i--){
        if(r[i]>r[p]) {swap(r[i],r[p]);
        break;}
    }
    reverse(r.begin()+p+1,r.end());
    return r;
}
int main()
{
    vector<int> v = {2, 4, 1, 7, 5, 0};
    vector<int>t=nextpermutation(v);
    for(auto c:t){
        cout<<c<<" ";
    }
}
```

## In-Built

Time
**O(n)**
Space O(1)


```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    next_permutation(v.begin(),v.end());
    for(auto x:v){
        cout<<x;
    }
}
```