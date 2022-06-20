## 102. Binary Tree Level Order Traversal

<p align="center">
    https://leetcode.com/problems/binary-tree-level-order-traversal
</P>

Given the `root` of a binary tree, return _the level order traversal of its nodes' values._ (i.e., from left to right, level by level).

**Constraints:**
- The number of nodes in the tree is in the range [0, 2000].
- -1000 <= Node.val <= 1000

<h4>EXAMPLES</h4>

```
Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]
```

```
Input: root = [1]
Output: [[1]]
```

```
Input: root = []
Output: []
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        queue<TreeNode*> q;
        vector<vector<int>> res;
        if (root==NULL) return res;
        q.push(root);
        while (!q.empty()) {
            int size = q.size();
            vector<int> level;
            for (int i = 0; i < size; i++) {
                TreeNode *node = q.front();
                q.pop();
                if (node->left!=NULL) q.push(node->left);
                if (node->right!=NULL) q.push(node->right);
                level.push_back(node->val);
            }
            res.push_back(level);
        }
        return res;
    }
};
```
