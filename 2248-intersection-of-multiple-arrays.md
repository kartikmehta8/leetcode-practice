## 2248. Intersection of Multiple Arrays

<p align="center">
    https://leetcode.com/problems/intersection-of-multiple-arrays
</P>

Given a 2D integer array `nums` where `nums[i]` is a non-empty array of **distinct** positive integers, return _the list of integers that are present in_ **each array** _of_ `nums` _sorted in_ **ascending order**. 

**Constraints:**
- 1 <= nums.length <= 1000
- 1 <= sum(nums[i].length) <= 1000
- 1 <= nums[i][j] <= 1000
- All the values of nums[i] are unique.


<h4>EXAMPLES</h4>

```
Input: nums = [[3,1,2,4,5],[1,2,3,4],[3,4,5,6]]
Output: [3,4]
Explanation: 
The only integers present in each of nums[0] = [3,1,2,4,5], nums[1] = [1,2,3,4], and nums[2] = [3,4,5,6] are 3 and 4, so we return [3,4].
```

```
Input: nums = [[1,2,3],[4,5,6]]
Output: []
Explanation: 
There does not exist any integer present both in nums[0] and nums[1], so we return an empty list [].
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> intersection(vector<vector<int>>& nums) {
        map<int, int> mp;
        set<int> s;
        vector<int> v;
        for (auto vectr: nums) {
            for (auto it: vectr) {
                mp[it]++;
                s.insert(it);
            }
        }
        for (auto it: s) {
            if (mp[it] == nums.size()) v.push_back(it);
        }
        return v;
    }
};
```
