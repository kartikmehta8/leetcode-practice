## 148. Sort List

<p align="center">
    https://leetcode.com/problems/sort-list
</P>

Given the `head` of a linked list, return _the list after sorting it in_ **ascending order**.

**Constraints:**
- The number of nodes in the list is in the range [0, 5 * 10^4].
- -10^5 <= Node.val <= 10^5


<h4>EXAMPLES</h4>

```
Input: head = [4,2,1,3]
Output: [1,2,3,4]
```

```
Input: head = [-1,5,3,4,0]
Output: [-1,0,3,4,5]
```

```
Input: head = []
Output: []
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    
    ListNode* createNode(int val) {
        ListNode* newNode = new ListNode();
        newNode->val = val;
        newNode->next = NULL;
        return newNode;
    }
    
    ListNode* sortList(ListNode* head) {
        vector<int> v;
        while (head != NULL) {
            v.push_back(head->val);
            head=head->next;
        }
        
        sort(v.begin(), v.end());
        
        ListNode *res = NULL, *x = NULL;
        for (auto it: v) {
            if (x == NULL) {
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
