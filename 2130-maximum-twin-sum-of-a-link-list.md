## 2130. Maximum Twin Sum of a Linked List

<p align="center">
    https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list
</P>

In a linked list of size `n`, where n is **even**, the ith node (**0-indexed**) of the linked list is known as the **twin** of the `(n-1-i)th` node, if `0 <= i <= (n / 2) - 1`.

- For example, if `n = 4`, then node `0` is the twin of node `3`, and node `1` is the twin of node `2`. These are the only nodes with twins for `n = 4`.

The **twin sum** is defined as the sum of a node and its twin.

Given the `head` of a linked list with even length, return _the_ **maximum twin sum** _of the linked list_.

**Constraints:**
- The number of nodes in the list is an even integer in the range [2, 105].
- 1 <= Node.val <= 105


<h4>EXAMPLES</h4>

```
Input: head = [5,4,2,1]
Output: 6
Explanation:
Nodes 0 and 1 are the twins of nodes 3 and 2, respectively. All have twin sum = 6.
There are no other nodes with twins in the linked list.
Thus, the maximum twin sum of the linked list is 6.
```

```
Input: head = [4,2,2,3]
Output: 7
Explanation:
The nodes with twins present in this linked list are:
- Node 0 is the twin of node 3 having a twin sum of 4 + 3 = 7.
- Node 1 is the twin of node 2 having a twin sum of 2 + 2 = 4.
Thus, the maximum twin sum of the linked list is max(7, 4) = 7. 
```

```
Input: head = [1,100000]
Output: 100001
Explanation:
There is only one node with a twin in the linked list having twin sum of 1 + 100000 = 100001.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int pairSum(ListNode* head) {
        stack<int> st;
        int count = 0;
        ListNode* t = head;
        while (t!=NULL) {
            count++;
            t=t->next;
        }
        int mid = count/2;
        while (mid) {
            st.push(head->val);
            head=head->next;
            mid--;
        }
        int max_sum = 0;
        while (head!=NULL) {
            int top = st.top();
            st.pop();
            int val = top+head->val;
            max_sum=max(max_sum, val);
            head=head->next;
        }
        return max_sum;
    }
};
```
