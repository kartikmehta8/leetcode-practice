## 1827. Minimum Operations to Make the Array Increasing

<p align="center">
    https://leetcode.com/problems/minimum-operations-to-make-the-array-increasing
</P>

You are given an integer array `nums` **(0-indexed)**. In one operation, you can choose an element of the array and increment it by `1`.

- For example, if `nums = [1,2,3]`, you can choose to increment `nums[1]` to make `nums = [1,3,3]`.

Return _the_ **minimum** _number of operations needed to make_ `nums` **strictly increasing**.

An array `nums` is **strictly increasing** if `nums[i] < nums[i+1]` for all `0 <= i < nums.length - 1`. An array of length `1` is trivially strictly increasing.

**Constraints:**
- 1 <= nums.length <= 5000
- 1 <= nums[i] <= 10^4


<h4>EXAMPLES</h4>

```
Input: nums = [1,1,1]
Output: 3
Explanation: You can do the following operations:
1) Increment nums[2], so nums becomes [1,1,2].
2) Increment nums[1], so nums becomes [1,2,2].
3) Increment nums[2], so nums becomes [1,2,3].
```

```
Input: nums = [1,5,2,4,1]
Output: 14
```

```
Input: nums = [8]
Output: 0
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int minOperations(vector<int>& nums) {
        int res = 0;
        if (nums.size() == 1) return 0;
        else {
            for (int i = 0; i < nums.size()-1; i++) {
                if (nums[i] < nums[i+1]) continue;
                else {
                    int t = nums[i]-nums[i+1]+1;
                    res += t;
                    nums[i+1] += t;
                }
            }
        }
        return res;
    }
};
```
