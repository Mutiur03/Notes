
### Naive way
Using  recursion
Time
**O(n)**
Space O(n.n!)

```cpp
#include <bits/stdc++.h>
using namespace std;
void permute(vector<vector<int>> &res, vector<int> &v, int inx)
{
    if (inx == v.size())
    {
        res.push_back(v);
        return;
    }
    for (int i = inx; i < v.size(); i++)
    {
        swap(v[i], v[inx]);
        permute(res, v, inx + 1);
        swap(v[i], v[inx]);
    }
}
int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    vector<vector<int>> res;
    permute(res, v, 0);
    for (auto x : res)
    {
        for (auto y : x)
        {
            cout << y << " ";
        }
        cout << endl;
    }
}
```

##  In-Built

Using next_permutation()
Time
**O(n.n!)**
Space O(n)
```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    sort(v.begin(), v.end());
    do
    {
        for (auto x : v)
        {
            cout << x << " ";
        }
        cout << endl;
    }while(next_permutation(v.begin(),v.end()));
}
```

Using prev_permutation()
Time
**O(n.n!)**
Space O(n)
```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {1, 2, 3, 4, 5};
    sort(v.begin(), v.end());
    reverse(v.begin(),v.end());
    do
    {
        for (auto x : v)
        {
            cout << x << " ";
        }
        cout << endl;
    }while(prev_permutation(v.begin(),v.end()));
}
```