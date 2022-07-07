## 287. Find the Duplicate Number

<p align="center">
    https://leetcode.com/problems/find-the-duplicate-number
</P>

Given an array of integers `nums` containing `n + 1` integers where each integer is in the range `[1, n]` inclusive.

There is only **one repeated number** in `nums`, return _this repeated number_.

You must solve the problem **without** modifying the array `nums` and uses only constant extra space.

**Constraints:**
- 1 <= n <= 105
- nums.length == n + 1
- 1 <= nums[i] <= n
- All the integers in nums appear only once except for precisely one integer which appears two or more times.


<h4>EXAMPLES</h4>

```
Input: nums = [1,3,4,2,2]
Output: 2
```

```
Input: nums = [3,1,3,4,2]
Output: 3
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        map<int, int> mp;
        for (auto it: nums) {
            mp[it]++;
            if (mp[it] == 2) return it;
        }
        return 0;
    }
};
```
