
```cpp
#include <bits/stdc++.h>
using namespace std;
int distinctSubstring(string str)
{
    set<string> result;
    for (int i = 0; i <= str.length(); i++)
    {
        for (int j = 1; j <= str.length() - i; j++)
        {
            result.insert(str.substr(i, j));
        }
    }
    return result.size();
}
int main()
{
    int t;
    cin >> t;
    while (t--)
    {
        string str;
        cin >> str;
        cout << (distinctSubstring(str)) << endl;
    }
}
```