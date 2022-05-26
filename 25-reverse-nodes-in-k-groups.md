## 25. Reverse Nodes in k-Group

<p align="center">
    https://leetcode.com/problems/reverse-nodes-in-k-group
</P>

Given the `head` of a linked list, reverse the nodes of the list `k` at a time, and return the modified list.

`k` is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of `k` then left-out nodes, in the end, should remain as it is.

You may not alter the values in the list's nodes, only nodes themselves may be changed.

**Constraints:**
- The number of nodes in the list is n.
- 1 <= k <= n <= 5000
- 0 <= Node.val <= 1000

<h4>EXAMPLES</h4>

```
Input: head = [1,2,3,4,5], k = 2
Output: [2,1,4,3,5]
```

```
Input: head = [1,2,3,4,5], k = 3
Output: [3,2,1,4,5]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    ListNode *createNode(int val) {
        ListNode *newNode = new ListNode();
        newNode->val = val;
        newNode->next = NULL;
        return newNode;
    }
    
    ListNode* reverseKGroup(ListNode* head, int k) {
        if (k == 1) return head;
        vector<int> v;
        while (head != NULL) {
            v.push_back(head->val);
            head = head->next;
        }
        int i = 0, j = k;
        while (j <= v.size()) {
            reverse(v.begin()+i, v.begin()+j);
            i = j;
            j += k;
        }
        ListNode *res = NULL, *x = NULL;
        for (auto it: v) {
            if (res == NULL) {
                x = createNode(it);
                res = x;
            } else {
                x->next = createNode(it);
                x = x->next;
            }
        }
        return res;
        
        return NULL;
    }
};
```
