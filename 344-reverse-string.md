## 344. Reverse String

<p align="center">
    https://leetcode.com/problems/reverse-string
</P>

Write a function that reverses a string. The input string is given as an array of characters `s`.

You must do this by modifying the input array _in-place_ with `O(1)` extra memory.

**Constraints:**
- 1 <= s.length <= 10^5
- s[i] is a printable ascii character.

<h4>EXAMPLES</h4>

```
Input: s = ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

```
Input: s = ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]

```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    void rev(vector<char>& s, int i, int j) {
        if (i >= j) return;
        swap(s[i], s[j]);
        rev(s, i+1, j-1);
    }
    
    void reverseString(vector<char>& s) {
        int i = 0, j = s.size()-1;
        rev(s, i, j);
    }
};
```
