## 921. Minimum Add to Make Parentheses Valid

<p align="center">
    https://leetcode.com/problems/minimum-add-to-make-parentheses-valid
</P>

A parentheses string is valid if and only if:

- It is the empty string,
- It can be written as `AB` (`A` concatenated with `B`), where `A` and `B` are valid strings, or
- It can be written as `(A)`, where `A` is a valid string.

You are given a parentheses string `s`. In one move, you can insert a parenthesis at any position of the string.

- For example, if `s = "()))"`, you can insert an opening parenthesis to be `"(()))"` or a closing parenthesis to be `"())))"`.

Return _the minimum number of moves required to make_ `s` _valid_.

**Constraints:**
- 1 <= s.length <= 1000
- s[i] is either '(' or ')'.


<h4>EXAMPLES</h4>

```
Input: s = "())"
Output: 1
```

```
Input: s = "((("
Output: 3
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int minAddToMakeValid(string s) {
        int res = 0, curr = 0;
        for (int i = 0; i < s.size(); i++) {
            if (s[i] == '(') curr++;
            else if (s[i] == ')' && curr <= 0) res++;
            else curr--;
        }
        return abs(res)+curr;
    }
};
```
