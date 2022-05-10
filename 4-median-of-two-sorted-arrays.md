## 4. Median of Two Sorted Arrays

<p align="center">
    https://leetcode.com/problems/median-of-two-sorted-arrays
</P>

Given two sorted arrays `nums1` and `nums2` of size `m` and `n` respectively, return **the median** of the two sorted arrays.

The overall run time complexity should be `O(log (m+n))`.

**Constraints:**
- nums1.length == m
- nums2.length == n
- 0 <= m <= 1000
- 0 <= n <= 1000
- 1 <= m + n <= 2000
- -10^6 <= nums1[i], nums2[i] <= 10^6



<h4>EXAMPLES</h4>

```
Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.
```

```
Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        multiset<int> ms;
        vector<int> v;
        for (auto it: nums1) ms.insert(it);
        for (auto it: nums2) ms.insert(it);
        for (auto it: ms) v.push_back(it);
        if (v.size()%2!=0) return v[v.size()/2];
        else return (double)(v[v.size()/2]+v[v.size()/2-1])/2;
    }
};
```
