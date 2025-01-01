Height and depth of any node in tree
```cpp
#include<bits/stdc++.h>

using namespace std;

const int N=1e5+5;

int height[N],depth[N];

vector<int>v[N];

void dfs(int vertex,int parent){

    for(auto child:v[vertex]){

        if(child==parent) continue;

        depth[child]=depth[vertex]+1;

        dfs(child,vertex);

        height[vertex]=max(height[vertex],height[child]+1);

    }

}

int main(){

    int n;

    cin>>n;

    for(int i=0; i<n-1; i++){

        int a,b;

        cin>>a>>b;

        v[a].push_back(b);

        v[b].push_back(a);

    }

    dfs(1,0);

    for(int i=1; i<=n; i++){

        cout<<depth[i]<<" "<<height[i]<<endl;

    }

}
```


### Precomputation in subtree

```cpp
#include<bits/stdc++.h>

using namespace std;

const int N=1e5+5;

vector<int>subtree_sum(N);

vector<int>v[N];

void dfs(int vertex,int parent){

    subtree_sum[vertex]+=vertex;

    for(auto child:v[vertex]){

        if(child==parent) continue;

        dfs(child,vertex);

        subtree_sum[vertex]+=subtree_sum[child];

    }

}

int main(){

    int n;

    cin>>n;

    for(int i=0; i<n-1; i++){

        int a,b;

        cin>>a>>b;

        v[a].push_back(b);

        v[b].push_back(a);

    }

    dfs(1,0);

    for(int i=1; i<=n; i++){

        cout<<subtree_sum[i]<<endl;

    }

}
```