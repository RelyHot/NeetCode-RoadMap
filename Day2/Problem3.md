### **Problem 3 : [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/description/)**

**Algorithm:** 

1. Create a HashSet to store all the values from nums.
2. Now For Each Element in Set if there is a element 1 less than it then skip it
3. Else set count = 1 and count the length of the sequence.
4. Check if it is Maximum or Not
5. return the Max Length.

```
class Solution {
    public int longestConsecutive(int[] nums) {
        HashSet <Integer> hset = new HashSet<>();
        int max = 0,c = 0,num1 = 0;
        for(int num: nums) hset.add(num);
        for(int num: hset){
            if(!hset.contains(num-1)){
                c = 1;
                num1 = num;
                while(hset.contains(num1+1)){c++;num1++;}
                max = Math.max(c,max);
            }
        }
        return max;
    }
}
```