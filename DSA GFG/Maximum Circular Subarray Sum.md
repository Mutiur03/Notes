
****Time Complexity****: O(n)  
****Space:**** O(1)
```cpp
#include <bits/stdc++.h>
using namespace std;
int maxC(vector<int>&v){
    int minSum=v[0];
    int mi=0;
    int maxSum=v[0];
    int ma=0;
    int t=0;
    for(int i=0; i<v.size(); i++){
        ma=max(ma+v[i],v[i]);
        maxSum=max(maxSum,ma);

        mi=min(mi+v[i],v[i]);
        minSum=min(minSum,mi);
  
        t+=v[i];
    }
  
    int n=maxSum;
    int cs=t-minSum;
    if(cs==0) return n;
    return max(cs,n);
}
int main()
{
    vector<int> v = {8, -8, 9, -9, 10, -11, 12};
    cout<<maxC(v);
}
```
