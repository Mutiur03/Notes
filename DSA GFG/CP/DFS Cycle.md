
```cpp
#include <bits/stdc++.h>

using namespace std;

class Solution {

public:

    bool dfs(int index,int parent,vector<vector<int>>&v,bool vis[]){

    vis[index]=true;

    bool cycle=false;

    for(auto child:v[index]){

        if(vis[child]&& child==parent) continue;

        if(vis[child]) return true;

        cycle |=dfs(child,index,v,vis);

    }

    return cycle;

}

    bool isCycle(vector<vector<int>>& adj) {

        bool vis[adj.size()];

        for(int i=0; i<adj.size(); i++)

            vis[i]=false;

        for(int i=0; i<adj.size(); i++){

        if(vis[i]==true) continue;

        if(dfs(i,-1,adj,vis)) return true;

        }

        return false;

    }

};

int main() {

    int tc;

    cin >> tc;

    while (tc--) {

        int V, E;

        cin >> V >> E;

        vector<vector<int>> adj(V);

        for (int i = 0; i < E; i++) {

            int u, v;

            cin >> u >> v;

            adj[u].push_back(v);

            adj[v].push_back(u);

        }

        Solution obj;

        bool ans = obj.isCycle(adj);

        if (ans)

            cout << "1\n";

        else

            cout << "0\n";

        cout << "~"

             << "\n";

    }

    return 0;

}
```