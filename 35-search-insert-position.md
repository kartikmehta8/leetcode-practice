## 35. Search Insert Position

<p align="center">
    https://leetcode.com/problems/search-insert-position
</P>

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with `O(log n)` runtime complexity.

**Constraints:**
- 1 <= nums.length <= 10^4
- -10^4 <= nums[i] <= 10^4
- nums contains distinct values sorted in ascending order.
- -10^4 <= target <= 10^4


<h4>EXAMPLES</h4>

```
Input: nums = [1,3,5,6], target = 5
Output: 2
```

```
Input: nums = [1,3,5,6], target = 2
Output: 1
```

```
Input: nums = [1,3,5,6], target = 7
Output: 4
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int i = 0, j = nums.size()-1, min_index = INT_MIN;
        while (i<=j) {
            int mid = (i+j)/2;
            if (nums[mid] >= target) {
                min_index = mid;
                j = mid-1;
            } else {
                i = mid+1;
            }
        }
        if (min_index == INT_MIN) return nums.size();
        return min_index;
    }
};
```
