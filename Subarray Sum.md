```cpp
int subarraySum(vector<int>& nums, int k) {
        vector<int>prefix(nums.size(),0);
        prefix[0]=nums[0];
        for(int i=1; i<nums.size(); i++){
            prefix[i]=prefix[i-1]+nums[i];
        }
        int count=0;
        unordered_map<int,int>m;
        for(auto c:prefix){
            if(c==k) count++;
            if(m.find(c-k)!=m.end()){
                count+=m[c-k];
            }
            m[c]++;
        }
        return count;
    }
```