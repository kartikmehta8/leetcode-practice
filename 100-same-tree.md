## 100. Same Tree

<p align="center">
    https://leetcode.com/problems/same-tree
</P>

Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

**Constraints:**
- The number of nodes in both trees is in the range [0, 100].
- -10^4 <= Node.val <= 10^4


<h4>EXAMPLES</h4>

```
Input: p = [1,2,3], q = [1,2,3]
Output: true
```

```
Input: p = [1,2], q = [1,null,2]
Output: false
```

```
Input: p = [1,2,1], q = [1,1,2]
Output: false
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    bool isSameTree(TreeNode* p, TreeNode* q) {
        if (p==NULL || q==NULL) return p==q;
        return (p->val==q->val) && isSameTree(p->left, q->left) && isSameTree(p->right, q->right);
    }
};
```
