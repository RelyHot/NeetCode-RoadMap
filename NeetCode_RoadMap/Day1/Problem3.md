### **Problem 3 : [Two Sum](https://leetcode.com/problems/two-sum/description/)**

**Algorithm 1:** 

1. Create a HashMap. Traverse Array Nums and for each num calculate the required number to reach target.
2. If the required is present in the HashMap return the array
3. Else Store the Num in HashMap.

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> hmap = new HashMap<>();
        for(int i=0;i<nums.length;i++){
            int a = hmap.getOrDefault(target - nums[i] , 12345);
            if(a == 12345) {hmap.put(nums[i],i); continue;}
            return new int[] {a,i};
        }
        return null;
    }
}
```

**Algorithm 2:** 

1. Two Pointer Approach.

```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i=1;i<nums.length;i++){
            for(int j=i;j<nums.length;j++){
                if(nums[j-i]+nums[j]==target) return new int[]{j-i,j};
            }
        }
        return new int[]{};
    }
}
```