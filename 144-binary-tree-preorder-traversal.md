## 144. Binary Tree Preorder Traversal

<p align="center">
    https://leetcode.com/problems/binary-tree-preorder-traversal
</P>

Given the `root` of a binary tree, return _the preorder traversal of its nodes' values_.

**Constraints:**
- The number of nodes in the tree is in the range [0, 100].
- -100 <= Node.val <= 100


<h4>EXAMPLES</h4>

```
Input: root = [1,null,2,3]
Output: [1,2,3]
```

```
Input: root = []
Output: []
```

```
Input: root = [1]
Output: [1]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> preorderTraversal(TreeNode* root) {
        
        stack<TreeNode*> s;
        vector<int> v;
        
        if (root == NULL) return v;
        
        TreeNode* curr = root;
        
        while (!s.empty() || curr != NULL) {
            while (curr != NULL) {
                v.push_back(curr->val);
                
                if (curr->right) s.push(curr->right);
                curr = curr->left;
            }
            
            if (s.empty() ==  false) {
                curr = s.top();
                s.pop();
            }
        }
        return v;
    }
};
```
