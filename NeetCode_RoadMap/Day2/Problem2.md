### **Problem 2 : [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/description/)**

**Algorithm 1:**    // Slower

1. Create 3 Arrays of Same lenght as Nums as Left, Right and Result.
2. In the Left Array Store the product of all the element before that index.
3. In the Right Arrat Store the Product of all the elements after that index.
4. In the Result array product both left and right and return the answer.

```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] l = new int[n];
        int[] r = new int[n];
        int[] ans = new int[n];

        l[0] = 1;
        for(int i=1;i<n;i++) l[i] = l[i-1] * nums[i-1];

        r[n-1] = 1;
        for(int i=n-2;i>=0;i--) r[i] = r[i+1] * nums[i+1];

        for(int i=0;i<n;i++) ans[i] = l[i] * r[i];

        return ans;
    }
}
```

**Algorithm 2:**    // Faster

1. In a Long Store the Product of all the elements and also count the number of zeros in nums.
2. Now if the Number of Zeros is 1. Then the element at location will be the product of all except zero. and everywhere else will be 0
3. If there are More than 1 Zeros in the Array the output will be a Array of Zeros.
4. If there are No zeros we divide each element with the product and store it there itself to return the array.

```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        long prod = 1;
        int zeros = 0;
        for(int i=0;i<nums.length;i++){
            if (nums[i] == 0) zeros++;
            else prod *= nums[i];
        }
        if(zeros == 1){
            for(int i=0;i<nums.length;i++){
                if(nums[i] == 0) nums[i] = (int)prod;
                else nums[i] = 0;
            }
        }
        else if(zeros > 1) for(int i=0;i<nums.length;i++) nums[i] = 0;
        else for(int i=0;i<nums.length;i++)nums[i] = (int) prod / nums[i];
        return nums;
    }
}
```