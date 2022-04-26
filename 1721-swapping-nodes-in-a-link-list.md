## 1721. Swapping Nodes in a Linked List

<p align="center">
    https://leetcode.com/problems/swapping-nodes-in-a-linked-list
</P>

You are given the `head` of a linked list, and an integer `k`.

Return the head of the linked list after **swapping** the values of the `kth` node from the beginning and the `kth` node from the end (the list is **1-indexed**).

**Constraints:**
- The number of nodes in the list is n.
- 1 <= k <= n <= 10^5
- 0 <= Node.val <= 100

<h4>EXAMPLES</h4>

```
Input: head = [1,2,3,4,5], k = 2
Output: [1,4,3,2,5]
```

```
Input: head = [7,9,6,6,7,8,3,0,9,5], k = 5
Output: [7,9,6,6,8,7,3,0,9,5]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    ListNode* createNode(int val) {
        ListNode* newNode = new ListNode();
        newNode->next = NULL;
        newNode->val = val;
        return newNode;
    }
    
    ListNode* swapNodes(ListNode* head, int k) {
        vector<int> v;
        while (head != NULL) {
            v.push_back(head->val);
            head = head->next;
        }
        swap(v[k-1], v[v.size()-k]);
        
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
    }
};
```
