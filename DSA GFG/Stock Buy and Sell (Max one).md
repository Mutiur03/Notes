
****Time Complexity:**** O(n)
****Auxiliary Space:**** O(1)
```cpp
using namespace std;
int main() {
    vector<int> prices = { 100, 180, 260, 310, 40, 535, 695 };
    int pro=0;
    int first=prices[0];
    int mi=first;
    int ma=0;
    for(int i=1; i<prices.size(); i++){
        mi=min(mi,prices[i]);
        ma=max(ma,prices[i]-mi);
    }
    cout<<ma;
}
```