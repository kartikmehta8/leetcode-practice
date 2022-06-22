## 217. Contains Duplicate

<p align="center">
    https://leetcode.com/problems/contains-duplicate
</P>

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Constraints:**
- 1 <= nums.length <= 10^5
- -10^9 <= nums[i] <= 10^9


<h4>EXAMPLES</h4>

```
Input: nums = [1,2,3,1]
Output: true
```

```
Input: nums = [1,2,3,4]
Output: false
```

```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        set<int> st;
        for (auto it: nums) {
            st.insert(it);
        }
        if (st.size() != nums.size()) return true;
        else return false;
    }
};
```
