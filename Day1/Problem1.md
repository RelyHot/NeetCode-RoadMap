### **Problem 1 : [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/submissions/1200567922/)**

**Algorithm:** 

1. Create a Hash Map and the elements of the array 1 by 1 in it.
2. Before Adding The Element Check if it is already present in the Hashmap or not
3. if It is already there return true
4. else at the end of the loop return false..

```
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashMap<Integer,Integer> hmap = new HashMap<>();
        for(int a : nums){
            if(hmap.containsKey(a)) return true;
            hmap.put(a,1);
        }
        return false;
    }
}
```