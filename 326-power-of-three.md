## 326. Power of Three

<p align="center">
    https://leetcode.com/problems/power-of-three
</P>

Given an integer `n`, return `true` _if it is a power of three. Otherwise, return_ `false`.

An integer `n` is a power of three, if there exists an integer `x` such that `n == 3x`.

**Constraints:**
- -2^31 <= n <= 2^31 - 1

<h4>EXAMPLES</h4>

```
Input: n = 27
Output: true
```

```
Input: n = 0
Output: false
```

```
Input: n = 9
Output: true
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool isPowerOfThree(int n) {
        if (n<0) return false;
        if (n==1) return true;
        while (true) {
            if (n%3!=0) return false;
            n /= 3;
            if (n==1) return true;
            if (n==0) return false;
        }
    }
};
```
