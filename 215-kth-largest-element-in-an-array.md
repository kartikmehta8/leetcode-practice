## 215. Kth Largest Element in an Array

<p align="center">
    https://leetcode.com/problems/kth-largest-element-in-an-array
</P>

Given an integer array `nums` and an integer `k`, return _the_ `kth` _largest element in the array_.

Note that it is the `kth` largest element in the sorted order, not the `kth` distinct element.

**Constraints:**
- 1 <= k <= nums.length <= 10^4
    -10^4 <= nums[i] <= 10^4


<h4>EXAMPLES</h4>

```
Input: nums = [3,2,1,5,6,4], k = 2
Output: 5
```

```
Input: nums = [3,2,3,1,2,4,5,5,6], k = 4
Output: 4
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int findKthLargest(vector<int>& nums, int k) {
        sort(nums.begin(), nums.end());
        return nums[nums.size()-k];
    }
};
```
