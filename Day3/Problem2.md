### **Problem 2 : [Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)**

**Algorithm:** 

1. Take 2 Pointers 1 at start and other one at End i and j respectively.
2. Now while I < J  check if sum of Elements at i and j is
3. Bigger Than Target Then decrease j;
4. Smaller Than Target then increase i;
5. Equal to Target then return i,j as a Array.

```
class Solution {
    public int[] twoSum(int[] nums, int t) {
        int i = 0, j = nums.length-1;
        while(i < j){
            if(nums[i] + nums[j] > t) j--;
            else if(nums[i] + nums[j] < t) i++;
            else if(nums[i] + nums[j] == t) return new int[]{i+1,j+1};
        }
        return null;
    }
}
```