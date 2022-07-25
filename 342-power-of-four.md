## 342. Power of Four

<p align="center">
    https://leetcode.com/problems/power-of-four
</P>

Given an integer `n`, return `true` _if it is a power of four. Otherwise, return_ `false`.

An integer `n` is a power of four, if there exists an integer `x` such that `n == 4x`.

**Constraints:**
- -2^31 <= n <= 2^31 - 1

<h4>EXAMPLES</h4>

```
Input: n = 16
Output: true
```

```
Input: n = 5
Output: false
```

```
Input: n = 1
Output: true
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool isPowerOfFour(int n) {
        if (n<0) return false;
        if (n==1) return true;
        while (true) {
            if (n%4!=0) return false;
            n /= 4;
            if (n==1) return true;
            if (n==0) return false;
        }
    }
};
```
