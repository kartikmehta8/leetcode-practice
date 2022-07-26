## 1221. Split a String in Balanced Strings

<p align="center">
    https://leetcode.com/problems/split-a-string-in-balanced-strings
</P>

**Balanced** strings are those that have an equal quantity of `'L'` and `'R'` characters.

Given a **balanced** string `s`, split it into some number of substrings such that:
- Each substring is balanced.

Return _the_ **maximum** _number of balanced strings you can obtain_.

**Constraints:**
- 2 <= s.length <= 1000
- s[i] is either 'L' or 'R'.
- s is a balanced string.


<h4>EXAMPLES</h4>

```
Input: s = "RLRRLLRLRL"
Output: 4
Explanation: s can be split into "RL", "RRLL", "RL", "RL", each substring contains same number of 'L' and 'R'.
```

```
Input: s = "RLRRRLLRLL"
Output: 2
Explanation: s can be split into "RL", "RRRLLRLL", each substring contains same number of 'L' and 'R'.
Note that s cannot be split into "RL", "RR", "RL", "LR", "LL", because the 2nd and 5th substrings are not balanced.
```

```
Input: s = "LLLLRRRR"
Output: 1
Explanation: s can be split into "LLLLRRRR".
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int balancedStringSplit(string s) {
        int res = 0, curr = 0;
        for (int i = 0; i < s.size(); i++) {
            if (s[i] == 'L') curr--;
            else curr++;
            
            if (curr == 0) res++;
        }
        
        return res;
    }
};
```
