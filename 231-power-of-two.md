## 231. Power of Two

<p align="center">
    https://leetcode.com/problems/power-of-two
</P>

Given an integer `n`, return `true` if it is a power of two. Otherwise, return `false`.
An integer `n` is a power of two, if there exists an integer `x` such that `n == 2x`.

**Constraints:**
- -2^31 <= n <= 2^31 - 1

<h4>EXAMPLES</h4>

```
Input: n = 1
Output: true
Explanation: 2^0 = 1
```

```
Input: n = 16
Output: true
Explanation: 2^4 = 16
```

```
Input: n = 3
Output: false
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if (n<=0) return false;
        int mask = n&(n-1);
        if (mask==0) return true;
        return false;
    }
};
```
