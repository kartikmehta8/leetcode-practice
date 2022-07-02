## 229. Majority Element II

<p align="center">
    https://leetcode.com/problems/majority-element-ii
</P>

Given an integer array of size `n`, find all elements that appear more than `⌊ n/3 ⌋` times.

**Constraints:**
- 1 <= nums.length <= 5 * 10^4
- -10^9 <= nums[i] <= 10^9


<h4>EXAMPLES</h4>

```
Input: nums = [3,2,3]
Output: [3]
```

```
Input: nums = [1]
Output: [1]
```

```
Input: nums = [1,2]
Output: [1,2]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> majorityElement(vector<int>& nums) {
        map<int, int> mp;
        set<int> st;
        vector<int> v;
        for (auto it: nums) {
            mp[it]++;
            st.insert(it);
        }
        for (auto it: st) {
            if (mp[it] > nums.size()/3) v.push_back(it);
        }
        return v;
    }
};
```
