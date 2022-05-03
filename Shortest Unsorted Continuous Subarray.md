## Shortest Unsorted Continuous Subarray-581

Given an integer array nums, you need to find one continuous subarray that if you only sort this subarray in ascending order, then the whole array will be sorted in ascending order.

Return the shortest such subarray and output its length.

 

Example 1:

Input: nums = [2,6,4,8,10,9,15]
Output: 5
Explanation: You need to sort [6, 4, 8, 10, 9] in ascending order to make the whole array sorted in ascending order.
Example 2:

Input: nums = [1,2,3,4]
Output: 0
Example 3:

Input: nums = [1]
Output: 0
 

Constraints:

1 <= nums.length <= 104
-105 <= nums[i] <= 105
 

Follow up: Can you solve it in O(n) time complexity?


### java Solution

```class Solution {
    public int findUnsortedSubarray(int[] N) {
        int len = N.length - 1, left = -1, right = -1,
            max = N[0], min = N[len];
        for (int i = 1; i <= len; i++) {
            int a = N[i], b = N[len-i];
            if (a < max) right = i;
            else max = a;
            if (b > min) left = i;
            else min = b;
        }
        return Math.max(0, left + right - len + 1);
    }
}

```

### Python Solution

```
class Solution {
    public int findUnsortedSubarray(int[] N) {
        int len = N.length - 1, left = -1, right = -1,
            max = N[0], min = N[len];
        for (int i = 1; i <= len; i++) {
            int a = N[i], b = N[len-i];
            if (a < max) right = i;
            else max = a;
            if (b > min) left = i;
            else min = b;
        }
        return Math.max(0, left + right - len + 1);
    }
}
```
