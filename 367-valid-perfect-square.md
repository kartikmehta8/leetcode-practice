## 367. Valid Perfect Square

<p align="center">
    https://leetcode.com/problems/valid-perfect-square
</P>

Given a **positive** integer _num_, write a function which returns True if _num_ is a perfect square else False.
**Follow up: Do not** use any built-in library function such as `sqrt`.

**Constraints:**
- 1 <= num <= 2^31 - 1

<h4>EXAMPLES</h4>

```
Input: num = 16
Output: true
```

```
Input: num = 14
Output: false
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool isPerfectSquare(int num) {
        int i = 1, j = num;
        if (num == 1) return true;
        while (i <= j) {
            long int mid = i + (j-i)/2;
            if (mid*mid == num) return true;
            else if (mid*mid>num) j = mid-1;
            else i = mid+1;
        }
        return false;
    }
};
```
