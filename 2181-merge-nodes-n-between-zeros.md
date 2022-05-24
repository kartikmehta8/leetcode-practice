## 2181. Merge Nodes in Between Zeros

<p align="center">
    https://leetcode.com/problems/merge-nodes-in-between-zeros
</P>

You are given the `head` of a linked list, which contains a series of integers **separated** by `0`'s. The **beginning** and **end** of the linked list will have `Node.val == 0`.

For **every** two consecutive `0`'s, **merge** all the nodes lying in between them into a single node whose value is the **sum** of all the merged nodes. The modified list should not contain any `0`'s.

Return the `head` of the _modified linked list_.

**Constraints:**
- The number of nodes in the list is in the range [3, 2 * 10^5].
- 0 <= Node.val <= 1000
- There are no two consecutive nodes with Node.val == 0.
- The beginning and end of the linked list have Node.val == 0.


<h4>EXAMPLES</h4>

```
Input: head = [0,3,1,0,4,5,2,0]
Output: [4,11]
Explanation: 
The above figure represents the given linked list. The modified list contains
- The sum of the nodes marked in green: 3 + 1 = 4.
- The sum of the nodes marked in red: 4 + 5 + 2 = 11.
```

```
Input: head = [0,1,0,3,0,2,2,0]
Output: [1,3,4]
Explanation: 
The above figure represents the given linked list. The modified list contains
- The sum of the nodes marked in green: 1 = 1.
- The sum of the nodes marked in red: 3 = 3.
- The sum of the nodes marked in yellow: 2 + 2 = 4.
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
    
    ListNode* mergeNodes(ListNode* head) {
        vector<int> v;
        int sum = 0;
        while (head->next != NULL) {
            if (head->val == 0) {
                v.push_back(sum);
                sum = 0;
            } else {
                sum += head->val;
            }
            head=head->next;
        }
        v.push_back(sum);
        ListNode *res = NULL, *x = NULL;
        for (auto it: v) {
            if (it == 0) continue;
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
