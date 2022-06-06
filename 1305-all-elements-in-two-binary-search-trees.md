## 1305. All Elements in Two Binary Search Trees

<p align="center">
    https://leetcode.com/problems/all-elements-in-two-binary-search-trees
</P>

Given two binary search trees `root1` and `root2`, return _a list containing all the integers from both trees sorted in_ **ascending order**.

**Constraints:**
- The number of nodes in each tree is in the range [0, 5000].
- -10^5 <= Node.val <= 10^5


<h4>EXAMPLES</h4>

```
Input: root1 = [2,1,4], root2 = [1,0,3]
Output: [0,1,1,2,3,4]
```

```
Input: root1 = [1,null,8], root2 = [8,1]
Output: [1,1,8,8]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    void traverse(TreeNode* root, vector<int> &v) {
        if (root!=NULL) {
            traverse(root->left, v);
            v.push_back(root->val);
            traverse(root->right, v);
        }
    }
    
    vector<int> getAllElements(TreeNode* root1, TreeNode* root2) {
        vector<int> v;
        traverse(root1, v);
        traverse(root2, v);
        sort(v.begin(), v.end());
        return v;
    }
};
```
