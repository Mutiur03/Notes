
#### Naive

****Time Complexity****: O(n^2)  
****Space:**** O(1)
```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {-2, 6, -3, -10, 0, 2};
    int maxP = 0;
    for (int i = 0; i < v.size(); i++)
    {
        int P = v[i];
        for (int j = i + 1; j < v.size(); j++)
        {
            P *= v[j];
            maxP = max(maxP, P);
        }
    }
    cout << maxP;
}
```

## As like Kadane's

Using minimum and maximum product ending at any index
****Time Complexity****: O(n)  
****Space:**** O(1)
```cpp
Not suugested😁
```

## Traversing from both direction

****Time Complexity****: O(n)  
****Space:**** O(1)
```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v = {-2, 6, -3, -10, 0, 2};
    int maxSum = v[0];
    int res = 0;
    int in=1,end=1;
    for (int i = 0; i < v.size(); i++)
    {
        if(in==0) in=1;
        if(end==0) end=1;
        in*=v[i];
        end*=v[v.size()-1-i];
        res=max(res,max(in,end));
    }
    cout << res;
}
```