## 53. Maximum Subarray

<p align="center">
    https://leetcode.com/problems/maximum-subarray
</P>

Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A **subarray** is a **contiguous** part of an array.

**Constraints:**
- 1 <= nums.length <= 10^5
- -104 <= nums[i] <= 10^4


<h4>EXAMPLES</h4>

```
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

```
Input: nums = [1]
Output: 1
```

```
Input: nums = [5,4,-1,7,8]
Output: 23
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int curr_sum = 0, max_sum = INT_MIN; 
        for (auto it: nums) {
            curr_sum += it;
            if (it > curr_sum) curr_sum = it;
            if (curr_sum > max_sum) max_sum = curr_sum;
        }
        return max_sum;
    }
};
```
