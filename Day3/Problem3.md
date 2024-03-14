### **Problem 3 : [3 Sum](https://leetcode.com/problems/3sum/description/)**

**Algorithm:** 

1. Create A Empty List of List to return the value and Also Sort Nums.
2. Now Take a pointer i from 0 to 2nd last element.
3. Now if i is either 0 or i if element at i is not same as element at i-1 then we move forward.
4. create 2 pointers left and right left being at i+1 and right being at last element of array.
5. and create a target as negetive of the number at i
6. Rest will use the same approach as last question as we have 2 pointers and a target to achieve.

```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> ans = new ArrayList<>();
        for (int i = 0; i < nums.length - 2; i++) {
            if (i == 0 || (i > 0 && nums[i] != nums[i - 1])) {
                int left = i + 1;
                int right = nums.length - 1;
                int target = -nums[i];
                while (left < right) {
                    if (nums[left] + nums[right] == target) {
                        ans.add(Arrays.asList(nums[i], nums[left], nums[right]));
                        while (left < right && nums[left] == nums[left + 1]) left++;
                        while (left < right && nums[right] == nums[right - 1]) right--;
                        left++;
                        right--;
                    } else if (nums[left] + nums[right] < target) {
                        left++;
                    } else {
                        right--;
                    }
                }
            }
        }
        return ans;
    }
}

```