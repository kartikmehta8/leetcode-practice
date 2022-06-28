## 2236. Root Equals Sum of Children

<p align="center">
    https://leetcode.com/problems/height-checker
</P>

You are given the `root` of a **binary** tree that consists of exactly `3` nodes: the root, its left child, and its right child.

Return `true` _if the value of the root is equal to the_ **sum** _of the values of its two children, or_ `false` _otherwise_.

**Constraints:**
- The tree consists only of the root, its left child, and its right child.
- -100 <= Node.val <= 100


<h4>EXAMPLES</h4>

```
Input: root = [10,4,6]
Output: true
Explanation: The values of the root, its left child, and its right child are 10, 4, and 6, respectively.
10 is equal to 4 + 6, so we return true.
```

```
Input: root = [5,3,1]
Output: false
Explanation: The values of the root, its left child, and its right child are 5, 3, and 1, respectively.
5 is not equal to 3 + 1, so we return false.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    bool checkTree(TreeNode* root) {
        if (root->val == root->left->val+root->right->val) return true;
        else return false;
    }
};
```
