## 1822. Sign of the Product of an Array

<p align="center">
    https://leetcode.com/problems/sign-of-the-product-of-an-array
</P>

There is a function `signFunc(x)` that returns:

- `1` if `x` is positive.
- `-1` if `x` is negative.
- `0` if `x` is equal to `0`.

You are given an integer array nums. Let `product` be the product of all values in the array `nums`.

Return `signFunc(product)`.

**Constraints:**
- 1 <= nums.length <= 1000
- -100 <= nums[i] <= 100

<h4>EXAMPLES</h4>

```
Input: nums = [-1,-2,-3,-4,3,2,1]
Output: 1
Explanation: The product of all values in the array is 144, and signFunc(144) = 1
```

```
Input: nums = [1,5,0,2,-3]
Output: 0
Explanation: The product of all values in the array is 0, and signFunc(0) = 0
```

```
Input: nums = [-1,1,-1,1,-1]
Output: -1
Explanation: The product of all values in the array is -1, and signFunc(-1) = -1
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int arraySign(vector<int>& nums) {
        int neg = 0;
        for (auto it: nums) {
            if (it == 0) return 0;
            else if (it < 0) neg++;
        }
        if (neg%2!=0) return -1;
        else return 1;
    }
};
```
