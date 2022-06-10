## 561. Array Partition I

<p align="center">
    https://leetcode.com/problems/array-partition-i
</P>

Given an integer array `nums` of `2n` integers, group these integers into `n` pairs `(a1, b1)`, `(a2, b2)`, ..., `(an, bn)` such that the sum of `min(ai, bi)` for all `i` is **maximized**. Return _the maximized sum_.

**Constraints:**
- 1 <= n <= 10^4
- nums.length == 2 * n
- -10^4 <= nums[i] <= 10^4


<h4>EXAMPLES</h4>

```
Input: nums = [1,4,3,2]
Output: 4
Explanation: All possible pairings (ignoring the ordering of elements) are:
1. (1, 4), (2, 3) -> min(1, 4) + min(2, 3) = 1 + 2 = 3
2. (1, 3), (2, 4) -> min(1, 3) + min(2, 4) = 1 + 2 = 3
3. (1, 2), (3, 4) -> min(1, 2) + min(3, 4) = 1 + 3 = 4
So the maximum possible sum is 4.
```

```
Input: nums = [6,2,6,5,1,2]
Output: 9
Explanation: The optimal pairing is (2, 1), (2, 5), (6, 6). min(2, 1) + min(2, 5) + min(6, 6) = 1 + 2 + 6 = 9.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        int res = 0;
        for (int i = 0; i < nums.size(); i = i+2) {
            res += nums[i];
        }
        return res;
    }
};
```
