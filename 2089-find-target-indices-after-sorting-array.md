## 2089. Find Target Indices After Sorting Array

<p align="center">
    https://leetcode.com/problems/find-target-indices-after-sorting-array
</P>

You are given a **0-indexed** integer array `nums` and a target element `target`.

A **target index** is an index `i` such that `nums[i] == target`.

Return _a list of the target indices of_ `nums` _after sorting_ `nums` _in_ **non-decreasing** _order_. If there are no target indices, return _an_ **empty** _list_. The returned list must be sorted in **increasing order**.

**Constraints:**
- 1 <= nums.length <= 100
- 1 <= nums[i], target <= 100


<h4>EXAMPLES</h4>

```
Input: nums = [1,2,5,2,3], target = 2
Output: [1,2]
Explanation: After sorting, nums is [1,2,2,3,5].
The indices where nums[i] == 2 are 1 and 2.
```

```
Input: nums = [1,2,5,2,3], target = 3
Output: [3]
Explanation: After sorting, nums is [1,2,2,3,5].
The index where nums[i] == 3 is 3.
```

```
Input: nums = [1,2,5,2,3], target = 5
Output: [4]
Explanation: After sorting, nums is [1,2,2,3,5].
The index where nums[i] == 5 is 4.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> targetIndices(vector<int>& nums, int target) {
        vector<int> v;
        sort(nums.begin(), nums.end());
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] ==  target) v.push_back(i);
        }
        return v;
    }
};
```
