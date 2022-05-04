## 104. Maximum Depth of Binary Tree

<p align="center">
    https://leetcode.com/problems/maximum-depth-of-binary-tree
</P>

Given the `root` of a binary tree, return its maximum depth.

A binary tree's **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Constraints:**
- The number of nodes in the tree is in the range [0, 10^4].
- -100 <= Node.val <= 100


<h4>EXAMPLES</h4>

```
Input: root = [3,9,20,null,null,15,7]
Output: 3
```

```
Input: root = [1,null,2]
Output: 2
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (!root) return 0;
        int l = maxDepth(root->left);
        int r = maxDepth(root->right);
        return max(l, r)+1;
        
    }
};
```
