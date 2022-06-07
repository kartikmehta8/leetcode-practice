## 147. Insertion Sort List

<p align="center">
    https://leetcode.com/problems/insertion-sort-list
</P>

Given the `head` of a singly linked list, sort the list using **insertion sort**, and return _the sorted list's head._

The steps of the **insertion sort** algorithm:

1. Insertion sort iterates, consuming one input element each repetition and growing a sorted output list.
2. At each iteration, insertion sort removes one element from the input data, finds the location it belongs within the sorted list and inserts it there.
3. It repeats until no input elements remain.

The following is a graphical example of the insertion sort algorithm. The partially sorted list (black) initially contains only the first element in the list. One element (red) is removed from the input data and inserted in-place into the sorted list with each iteration.

**Constraints:**
- The number of nodes in the list is in the range [1, 5000].
- -5000 <= Node.val <= 5000



<h4>EXAMPLES</h4>

```
Input: head = [4,2,1,3]
Output: [1,2,3,4]
```

```
Input: head = [-1,5,3,4,0]
Output: [-1,0,3,4,5]
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
    
    ListNode* insertionSortList(ListNode* head) {
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
