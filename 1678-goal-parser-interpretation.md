## 1678. Goal Parser Interpretation

<p align="center">
    https://leetcode.com/problems/goal-parser-interpretation
</P>

You own a **Goal Parser** that can interpret a string `command`. The `command` consists of an alphabet of `"G"`, `"()"` and/or `"(al)"` in some order. The Goal Parser will interpret `"G"` as the string `"G"`, `"()"` as the string `"o"`, and `"(al)"` as the string `"al"`. The interpreted strings are then concatenated in the original order.

Given the string `command`, return the **_Goal Parser_**'s interpretation of `command`.

**Constraints:**
- 1 <= command.length <= 100
- command consists of "G", "()", and/or "(al)" in some order.



<h4>EXAMPLES</h4>

```
Input: command = "G()(al)"
Output: "Goal"
Explanation: The Goal Parser interprets the command as follows:
G -> G
() -> o
(al) -> al
The final concatenated result is "Goal".
```

```
Input: command = "G()()()()(al)"
Output: "Gooooal"
```

```
Input: command = "(al)G(al)()()G"
Output: "alGalooG"
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    string interpret(string command) {
        string res = "";
        for (int i = 0; i < command.size(); i++) {
            if (command[i]=='G') res += "G";
            else if (command[i]=='(' && command[i+1]==')') {
                res+="o";
                i++;
            }
            else {
                i  += 3;
                res+="al";
            }
        }
        return res;
    }
};
```
