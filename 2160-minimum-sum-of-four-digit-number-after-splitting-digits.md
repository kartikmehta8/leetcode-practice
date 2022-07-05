## 2160. Minimum Sum of Four Digit Number After Splitting Digits

<p align="center">
    https://leetcode.com/problems/minimum-sum-of-four-digit-number-after-splitting-digits
</P>

You are given a **positive** integer `num` consisting of exactly four digits. Split `num` into two new integers `new1` and `new2` by using the **digits** found in `num`. **Leading zeros** are allowed in `new1` and `new2`, and **all** the digits found in `num` must be used.

- For example, given `num = 2932`, you have the following digits: two `2`'s, one 9 and one `3`. Some of the possible pairs `[new1, new2]` are `[22, 93]`, `[23, 92]`, `223, 9]` and `[2, 329]`.

Return _the_ **minimum** _possible sum of_ `new1` _and_ `new2`.

**Constraints:**
- 1000 <= num <= 9999

<h4>EXAMPLES</h4>

```
Input: num = 2932
Output: 52
Explanation: Some possible pairs [new1, new2] are [29, 23], [223, 9], etc.
The minimum sum can be obtained by the pair [29, 23]: 29 + 23 = 52.
```

```
Input: num = 4009
Output: 13
Explanation: Some possible pairs [new1, new2] are [0, 49], [490, 0], etc. 
The minimum sum can be obtained by the pair [4, 9]: 4 + 9 = 13.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int minimumSum(int num) {
        int dig1 = num%10;
        num /= 10;
        int dig2 = num%10;
        num /= 10;
        int dig3 = num%10;
        num /= 10;
        int dig4 = num%10;
        
        int arr[4] = {dig1, dig2, dig3, dig4};
        sort(arr, arr+4);
        
        return (arr[0]*10+arr[3])+(arr[1]*10+arr[2]);
    }
};
```
