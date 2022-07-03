## 260. Single Number III

<p align="center">
    https://leetcode.com/problems/single-number-iii
</P>

Given an integer array `nums`, in which exactly two elements appear only once and all the other elements appear exactly twice. Find the two elements that appear only once. You can return the answer in **any order**.

You must write an algorithm that runs in linear runtime complexity and uses only constant extra space.

**Constraints:**
- 2 <= nums.length <= 3 * 10^4
- -2^31 <= nums[i] <= 2^31 - 1
- Each integer in nums will appear twice, only two integers will appear once.

<h4>EXAMPLES</h4>

```
Input: nums = [1,2,1,3,2,5]
Output: [3,5]
Explanation:  [5, 3] is also a valid answer.
```

```
Input: nums = [-1,0]
Output: [-1,0]
```

```
Input: nums = [0,1]
Output: [1,0]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> singleNumber(vector<int>& nums) {
        map<int, int> mp;
        set<int> st;
        vector<int> v;
        for (auto it: nums) {
            mp[it]++;
            st.insert(it);
        }
        for (auto it: st) {
            if (mp[it]==1) v.push_back(it);
        }
        return v;
    }
};
```
