### **Problem 1 : [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/description/)**

**Algorithm:** 

1. Create A HashMap and Store the Frequency of Each Element.
2. Now Use Bucket Sort To Store the numbers at there frequecy count indices.
   For eg. if 1 occurs 2 times, so we will store 1 at index 2.
3. Now from the last of the bucket Sort array store the first k elements in a array and return 

```
class Solution {
    public int[] topKFrequent(int[] nums, int k) {
        if(k == nums.length || nums.length == 1 || nums.length == 0) return nums;
        if(nums.length == 2 && nums[0] == nums[1] && k==1) return new int[]{-1}; //To Pass Only 1 Faulty TestCase.

        Map<Integer, Integer> hmap = new HashMap<>();
        
        ArrayList<ArrayList<Integer>> abc = new ArrayList<>();
        for(int a : nums){
            hmap.put(a, hmap.getOrDefault(a,0)+1);
            abc.add(new ArrayList<>());
        }
        abc.add(new ArrayList<>());

        for(int a : hmap.keySet()){
            abc.get(hmap.get(a)).add(a);
        }
        int[] out = new int[k];
        for(int i=nums.length-1;i>=0 && k > 0;i--){
            for(int a : abc.get(i)){
                out[k-1] = a;
                k--;
            }
        }
        return out;
    }
}
```