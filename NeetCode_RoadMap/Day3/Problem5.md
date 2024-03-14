### **Problem 5 : [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/description/)**

**Algorithm:** 

1. Start Same With 2 Pointer ans 2 Variables maxRight and maxLeft.
2. while i < j, if left height is greater than right one check for maxLeft is greater than height, if yes then replace it else add the max - height to the answer and increment left
3. otherwise if left is smaller than right then we check for maxRight is greater than height, if yes then replace it else add the max - height to the answer and decrement right.
4. return the answer.

```
class Solution {
    public int trap(int[] height) {
        int l = 0, r = height.length-1;
        int maxRight = 0, maxLeft = 0;
        int ans = 0;
        while(l<r){
            if (height[l] <= height[r]) {
                if (height[l] >= maxLeft) {
                    maxLeft = height[l];
                } else {
                    ans += maxLeft - height[l];
                }
                l++;
            } else {
                if (height[r] >= maxRight) {
                    maxRight = height[r];
                } else {
                    ans += maxRight - height[r];
                }
                r--;
            }
        }
        return ans;
    }
}
```