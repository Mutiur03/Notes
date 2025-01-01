
```cpp
#include <bits/stdc++.h>
using namespace std;
const int N = 1e5 + 5;
vector<bool> vis(N, false);
vector<int> v[N];
vector<int>level(N);
void bfs(int source)
{
    queue<int> q;
    q.push(source);
    vis[source] = true;
    level[source]=0;
    while (!q.empty())
    {
        int cur = q.front();
        q.pop();
        for (auto child : v[cur])
        {
            if (!vis[child])
            {   q.push(child);
                vis[child] = true;
                level[child]=level[cur]+1;
            }
        }
    }
}
int main()
{
    int n, e;
    cin >> n >> e;
    for (int i = 0; i < n; i++)
    {
        int a, b;
        cin >> a >> b;
        v[a].push_back(b);
        v[b].push_back(a);
    }
    bfs(1);
    for(int i=1; i<=n; i++){
        cout<<level[i]<<endl;
    }
}
```