### **Problem 1 : [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)**

**Algorithm 1:** 

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
**Algorithm 2:** 

1. Create A HashSet. 
2. Iterate through the Array if the element is in the set return True else return False.

```
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> set=new HashSet<>();
        for(int num:nums)
            if(!set.add(num))
                return true;
        return false;
    }
}
```