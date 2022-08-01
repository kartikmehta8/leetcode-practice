## 1323. Maximum 69 Number

<p align="center">
    https://leetcode.com/problems/maximum-69-number
</P>

You are given a positive integer `num` consisting only of digits `6` and `9`.

Return _the maximum number you can get by changing_ **at most** _one digit (_`6` _becomes_ `9`_, and_ `9` _becomes_ `6`_)_.

**Constraints:**
- 1 <= num <= 10^4
- num consists of only 6 and 9 digits.


<h4>EXAMPLES</h4>

```
Input: num = 9669
Output: 9969
Explanation: 
Changing the first digit results in 6669.
Changing the second digit results in 9969.
Changing the third digit results in 9699.
Changing the fourth digit results in 9666.
The maximum number is 9969.
```

```
Input: num = 9996
Output: 9999
Explanation: Changing the last digit 6 to 9 results in the maximum number.
```

```
Input: num = 9999
Output: 9999
Explanation: It is better not to apply any change.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int maximum69Number (int num) {
        vector<int> v;
        while (num != 0) {
            v.push_back(num%10);
            num /= 10;
        }
        int res = 0, size = v.size()-1, t = 1;
        for (int i = v.size()-1; i >= 0; i--) {
            if (v[i] == 9) res += v[i]*pow(10, size);
            else if (v[i] == 6 && t == 1) {
                res += 9*pow(10, size);
                t = 0;
            }
            else res += v[i]*pow(10, size);
            size--;
        }
        
        return res;
    }
};
```
