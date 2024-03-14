### **Problem 4 : [Container With Most Water](https://leetcode.com/problems/container-with-most-water/description/)**

**Algorithm:** 

1. Take 2 Pointer i=0, j = n-1;
2. And a MaxArea to start with.
3. Now well work till i is less than j. find the min height of i and j position.
4. And also find the area with respect to it.
5. And iterate i till height of i is less than the min and similarly do with j as well also keep in mind to keep checking if i exceeds j.

```
class Solution {
    public int maxArea(int[] h) {
        int i = 0, j = h.length - 1;
        int maxArea = Integer.MIN_VALUE;
        while(i<j){
            int c = Math.min(h[j], h[i]);
            maxArea = Math.max(maxArea,(j-i) * c);
            while(i<j && h[i]<=c) i++;
            while(i<j && h[j]<=c) j--;
        }
        return maxArea;
    }
}
```