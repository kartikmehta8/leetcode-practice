## 1351. Count Negative Numbers in a Sorted Matrix

<p align="center">
    https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix
</P>

Given a `m x n` matrix `grid` which is sorted in non-increasing order both row-wise and column-wise, return _the number of_ **negative** _numbers in_ `grid`.

**Constraints:**
- m == grid.length
- n == grid[i].length
- 1 <= m, n <= 100
- -100 <= grid[i][j] <= 100


<h4>EXAMPLES</h4>

```
Input: grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
Output: 8
Explanation: There are 8 negatives number in the matrix.
```

```
Input: grid = [[3,2],[1,0]]
Output: 0
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int countNegatives(vector<vector<int>>& grid) {
        int count = 0;
        for (auto row: grid) {
            for (int i = 0; i < row.size(); i++) {
                if (row[i] < 0) {
                    count += row.size()-i;
                    break;
                }
            }
        }
        return count;
    }
};
```
