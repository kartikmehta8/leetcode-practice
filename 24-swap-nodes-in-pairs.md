## 24. Swap Nodes in Pairs

<p align="center">
    https://leetcode.com/problems/swap-nodes-in-pairs
</P>

Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)

**Constraints:**
- The number of nodes in the list is in the range [0, 100].
- 0 <= Node.val <= 100


<h4>EXAMPLES</h4>

```
Input: head = [1,2,3,4]
Output: [2,1,4,3]
```

```
Input: head = []
Output: []
```

```
Input: head = [1]
Output: [1]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    ListNode* swapPairs(ListNode* head) {
        if (head==NULL) return NULL;
        if (head->next==NULL) return head;
        int t = head->val;
        head->val = head->next->val;
        head->next->val = t;
        swapPairs(head->next->next);
        return head;
    }
};
```
