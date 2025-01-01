```cpp
#include<bits/stdc++.h>
using namespace std;
const int N=1e5+5;
vector<int>v[N];
bool vis[N];
void dfs(int index){
    vis[index]=true;
    for(auto child:v[index]){
        if(vis[child]) continue;
        dfs(child);
    }
}
  
int main(){
    int n,e;
    cin>>n>>e;
    for(int i=0; i<e; i++){
        int a,b;
        cin>>a>>b;
        v[a].push_back(b);
        v[b].push_back(a);
    }
    int count=0;
   for(int i=1; i<=n; i++){
        if(vis[i]==true) continue;
        dfs(i);
        count++;
    }
    cout<<count<<endl;
    return 0;
}
```