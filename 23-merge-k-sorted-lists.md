## 23. Merge k Sorted Lists

<p align="center">
    https://leetcode.com/problems/merge-k-sorted-lists
</P>

You are given an array of `k` linked-lists `lists`, each linked-list is sorted in ascending order.
Merge all the linked-lists into one sorted linked-list and return it.

**Constraints:**
- k == lists.length
- 0 <= k <= 10^4
- 0 <= lists[i].length <= 500
- -10^4 <= lists[i][j] <= 10^4
- lists[i] is sorted in ascending order.
- The sum of lists[i].length will not exceed 10^4

<h4>EXAMPLES</h4>

```
Input: lists = []
Output: []
```

```
Input: lists = [[1,4,5],[1,3,4],[2,6]]
Output: [1,1,2,3,4,4,5,6]
Explanation: The linked-lists are:
[
  1->4->5,
  1->3->4,
  2->6
]
merging them into one sorted list:
1->1->2->3->4->4->5->6
```

```
Input: lists = [[]]
Output: []
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
    
    ListNode* mergeKLists(vector<ListNode*>& lists) {
        vector<int> v;
        for (auto linkList: lists) {
            while (linkList != NULL) {
                v.push_back(linkList->val);
                linkList = linkList->next;
            }
        }
        sort(v.begin(), v.end());
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
