
## My Process 

****Time Complexity****: O(n)  
****Space:**** O(n)
```cpp
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin >> n;
    vector<int> v(n);
    for (int i = 0; i < n; i++)
    {
        cin >> v[i];
    }
    int m = *max_element(v.begin(), v.end());
    vector<int> c(m + 1, 0);
    for (int i = 0; i < n; i++)
    {
        if (v[i] > 0)
        {
            c[v[i]] = v[i];
        }
    }
    for (int i = 1; i <= m + 1; i++)
    {
        if (c[i] != i)
        {
            cout << i;
            return 0;
        }
    }
}
```
