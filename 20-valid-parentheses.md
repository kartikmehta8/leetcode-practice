## Valid Parenthesis

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:
- Open brackets must be closed by the same type of brackets.
- Open brackets must be closed in the correct order.

Constraints:
- 1 <= s.length <= 104
- s consists of parentheses only '()[]{}'.


```
**Input:** s = "()"
**Output:** true
```

```

class Solution {
public:
    bool isValid(string st) {
        stack<char> s;
        for (int i = 0; i < st.size(); i++) {
            if (s.size() == 0) {
                if (st[i] == ')' || st[i] == ']' || st[i] == '}') return false;
                 else {
                s.push(st[i]);
                continue;
                 }
            }
            if (st[i] == '(' || st[i] == '[' || st[i] == '{') s.push(st[i]);
            else {
                if (st[i] == ')') {
                    if (s.top() == '(') s.pop();
                    else return false;
                }
                if (st[i] == '}') {
                    if (s.top() == '{') s.pop();
                    else return false;
                }
                if (st[i] == ']') {
                    if (s.top() == '[') s.pop();
                    else return false;
                }
            }
        }
        if (s.empty()) return true;
        else return false;
    }
};
```

[Question Link](https://leetcode.com/problems/valid-parentheses/)
