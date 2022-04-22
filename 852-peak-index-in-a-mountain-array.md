## 852. Peak Index in a Mountain Array

<p align="center">
    https://leetcode.com/problems/peak-index-in-a-mountain-array
</P>

Let's call an array `arr` a **mountain** if the following properties hold:
- `arr.length >= 3`
- There exists some `i` with `0 < i < arr.length - 1` such that:
- - `arr[0] < arr[1] < ... arr[i-1] < arr[i]`
- - `arr[i] > arr[i+1] > ... > arr[arr.length - 1]`

Given an integer array `arr` that is **guaranteed** to be a mountain, return any `i` such that `arr[0] < arr[1] < ... arr[i - 1] < arr[i] > arr[i + 1] > ... > arr[arr.length - 1]`.

**Constraints:**
- `3 <= arr.length <= 10^4`
- `0 <= arr[i] <= 10^6`
- `arr` is **guaranteed** to be a mountain array.


<h4>EXAMPLES</h4>

```
Input: arr = [0,1,0]
Output: 1
```

```
Input: arr = [0,2,1,0]
Output: 1
```

```
Input: arr = [0,10,5,2]
Output: 1
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    int peakIndexInMountainArray(vector<int>& arr) {
        int i = 0, j = arr.size()-1;
        while (true) {
            int mid = (i+j)/2;
            if (arr[mid-1] < arr[mid] && arr[mid] > arr[mid+1]) return  mid;
            else if (arr[mid-1] > arr[mid]) j = mid;
            else if (arr[mid+1] > arr[mid]) i = mid;
        }
        return -1;
    }
};
```
