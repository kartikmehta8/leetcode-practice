## 92. Reverse Linked List II

<p align="center">
    https://leetcode.com/problems/reverse-linked-list-ii
</P>

Given the `head` of a singly linked list and two integers `left` and `right` where `left <= right`, reverse the nodes of the list from position `left` to position `right`, and return the _reversed list_.

**Constraints:**
- The number of nodes in the list is n.
- 1 <= n <= 500
- -500 <= Node.val <= 500
- 1 <= left <= right <= n


<h4>EXAMPLES</h4>

```
Input: head = [1,2,3,4,5], left = 2, right = 4
Output: [1,4,3,2,5]
```

```
Input: head = [5], left = 1, right = 1
Output: [5]
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
    
    ListNode* reverseBetween(ListNode* head, int left, int right) {
        vector<int> v;
        while (head != NULL) {
            v.push_back(head->val);
            head = head->next;
        }
        reverse(v.begin()+left-1, v.begin()+right);
        
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
