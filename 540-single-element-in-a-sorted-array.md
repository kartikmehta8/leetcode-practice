## 540. Single Element in a Sorted Array

<p align="center">
    https://leetcode.com/problems/single-element-in-a-sorted-array
</P>

You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once.

Return _the single element that appears only once_.

Your solution must run in `O(log n)` time and `O(1)` space.

**Constraints:**
- 1 <= nums.length <= 10^5
- 0 <= nums[i] <= 10^5


<h4>EXAMPLES</h4>

```
Input: nums = [1,1,2,3,3,4,4,8,8]
Output: 2
```

```
Input: nums = [3,3,7,7,10,11,11]
Output: 10
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int singleNonDuplicate(vector<int>& nums) {
        int res = 0;
        for (auto it: nums) res ^= it;
        return res;
    }
};
```
