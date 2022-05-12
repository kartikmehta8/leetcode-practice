## 43. Multiply Strings

<p align="center">
    https://leetcode.com/problems/multiply-strings
</P>

Given two non-negative integers `num1` and `num2` represented as strings, return the product of `num1` and `num2`, also represented as a string.

**Note:** You must not use any built-in BigInteger library or convert the inputs to integer directly.

**Constraints:**
- 1 <= num1.length, num2.length <= 200
- num1 and num2 consist of digits only.
- Both num1 and num2 do not contain any leading zero, except the number 0 itself.



<h4>EXAMPLES</h4>

```
Input: num1 = "2", num2 = "3"
Output: "6"
```

```
Input: num1 = "123", num2 = "456"
Output: "56088"
```

<h4>SOLUTION</h4>

```
class Solution:
    def multiply(self, num1: str, num2: str) -> str:
        return str(int(num1)*int(num2))
```
