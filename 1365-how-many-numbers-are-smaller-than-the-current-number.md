## 1365. How Many Numbers Are Smaller Than the Current Number

<p align="center">
    https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number
</P>

Given the array `nums`, for each `nums[i]` find out how many numbers in the array are smaller than it. That is, for each `nums[i]` you have to count the number of valid `j's` such that `j != i` **and** `nums[j] < nums[i]`.

Return the answer in an array.

**Constraints:**
- 2 <= nums.length <= 500
- 0 <= nums[i] <= 100


<h4>EXAMPLES</h4>

```
Input: nums = [8,1,2,2,3]
Output: [4,0,1,1,3]
Explanation: 
For nums[0]=8 there exist four smaller numbers than it (1, 2, 2 and 3). 
For nums[1]=1 does not exist any smaller number than it.
For nums[2]=2 there exist one smaller number than it (1). 
For nums[3]=2 there exist one smaller number than it (1). 
For nums[4]=3 there exist three smaller numbers than it (1, 2 and 2).
```

```
Input: nums = [6,5,4,8]
Output: [2,1,0,3]
```

```
Input: nums = [7,7,7,7]
Output: [0,0,0,0]
```

<h4>SOLUTION</h4>

```
class Solution {
public:
    vector<int> smallerNumbersThanCurrent(vector<int>& nums) {
        vector<int> v;
        for (int i = 0; i < nums.size(); i++) {
            int num = nums[i], count = 0;
            for (int j = 0; j < nums.size(); j++) {
                if (i == j) continue;
                if (nums[j] < num) count++;
            }
            v.push_back(count);
        }
        return v;
    }
};
```
