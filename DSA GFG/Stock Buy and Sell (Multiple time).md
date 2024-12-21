
***Time Complexity***: O(n)  
***Space:*** O(1)
```cpp
int main() {
    vector<int> prices = { 100, 180, 260, 310, 40, 535, 695 };
    int pro=0;
    for(int i=1; i<prices.size(); i++){
        if(prices[i]>=prices[i-1]){
            pro+=prices[i]-prices[i-1];
        }
    }
    cout<<pro;
}
```
