## 1460. Make Two Arrays Equal by Reversing Sub-arrays

<p align="center">
    https://leetcode.com/problems/make-two-arrays-equal-by-reversing-sub-arrays
</P>

You are given two integer arrays of equal length `target` and `arr`. In one step, you can select any **non-empty sub-array** of `arr` and reverse it. You are allowed to make any number of steps.

Return `true` _if you can make_ `arr` _equal to_ `target` _or_ `false` _otherwise_.

**Constraints:**
- target.length == arr.length
- 1 <= target.length <= 1000
- 1 <= target[i] <= 1000
- 1 <= arr[i] <= 1000


<h4>EXAMPLES</h4>

```
Input: target = [1,2,3,4], arr = [2,4,1,3]
Output: true
Explanation: You can follow the next steps to convert arr to target:
1- Reverse sub-array [2,4,1], arr becomes [1,4,2,3]
2- Reverse sub-array [4,2], arr becomes [1,2,4,3]
3- Reverse sub-array [4,3], arr becomes [1,2,3,4]
There are multiple ways to convert arr to target, this is not the only way to do so.
```

```
Input: target = [7], arr = [7]
Output: true
Explanation: arr is equal to target without any reverses.
```

```
Input: target = [3,7,9], arr = [3,7,11]
Output: false
Explanation: arr does not have value 9 and it can never be converted to target.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool canBeEqual(vector<int>& target, vector<int>& arr) {
        sort(target.begin(), target.end());
        sort(arr.begin(), arr.end());
        for (int i = 0; i < target.size(); i++) {
            if (target[i] != arr[i]) return false;
        }
        return true;
    }
};
```
