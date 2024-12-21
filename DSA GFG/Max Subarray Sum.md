
### Naive
****Time Complexity****: O(n^2)  
Space O(1)
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={2, 3, -8, 7, -1, 2, 3};
    int maxSum=0;
    for(int i=0; i<v.size(); i++){
        int sum=v[i];
        for(int j=i+1; j<v.size(); j++){
            sum+=v[j];
            maxSum=max(maxSum,sum);
        }
    }
    cout<<maxSum;
}
```


## Using Kadane's Algorithm

When the total sum is less than 0 then from there start a new maxSum
****Time Complexity****: O(n)  
****Space:**** O(1)
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>v={2, 3, -8, 7, -1, 2, 3};
    int maxSum=v[0];
    int res=maxSum;
    for(int i=1; i<v.size(); i++){
        maxSum=max(maxSum+v[i],v[i]);
        res=max(res,maxSum);
    }
    cout<<res;
}
```