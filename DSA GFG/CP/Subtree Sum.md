
```cpp
#include <bits/stdc++.h>

using namespace std;

const int N = 1e5 + 5;

vector<int> subtree_sum(N);

vector<int> v[N];

void dfs(int vertex, int parent)

{

    subtree_sum[vertex] += vertex;

    for (auto child : v[vertex])

    {

        if (child == parent)

            continue;

        dfs(child, vertex);

        subtree_sum[vertex] += subtree_sum[child];

    }

}

int main()

{

    int n;

    cin >> n;

    for (int i = 0; i < n - 1; i++)

    {

        int a, b;

        cin >> a >> b;

        v[a].push_back(b);

        v[b].push_back(a);

    }

    dfs(1, 0);

    for (int i = 1; i <= n; i++)

    {

        cout << subtree_sum[i] << endl;

    }

}
```