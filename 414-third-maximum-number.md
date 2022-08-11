## 414. Third Maximum Number

<p align="center">
    https://leetcode.com/problems/third-maximum-number
</P>

Given an integer array `nums`, return _the_ **third distinct maximum** _number in this array. If the third maximum does not exist, return the_ **maximum** _number_.

**Constraints:**
- 1 <= nums.length <= 10^4
- -2^31 <= nums[i] <= 2^31 - 1


<h4>EXAMPLES</h4>

```
Input: nums = [3,2,1]
Output: 1
Explanation:
The first distinct maximum is 3.
The second distinct maximum is 2.
The third distinct maximum is 1.
```

```
Input: nums = [1,2]
Output: 2
Explanation:
The first distinct maximum is 2.
The second distinct maximum is 1.
The third distinct maximum does not exist, so the maximum (2) is returned instead.
```

```
Input: nums = [2,2,3,1]
Output: 1
Explanation:
The first distinct maximum is 3.
The second distinct maximum is 2 (both 2's are counted together since they have the same value).
The third distinct maximum is 1.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int thirdMax(vector<int>& nums) {
        set<int> st;
        vector<int> v;
        for (auto it: nums) {
            st.insert(it);
        }
        for (auto it: st) v.push_back(it);
        if (v.size() >= 3) {
            return v[v.size()-3];
        } else {
            return v[v.size()-1];
        }
    }
};
```
