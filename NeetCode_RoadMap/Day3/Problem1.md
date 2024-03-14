### **Problem 1 : [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)**

**Algorithm:** 

1. Convert String s to LowerCase and convert to it Alpha Numeric.
2. Now Create 2 Pointers and keep checking for all the elements if equal or not.
3. if not then return false.
4. else increment i and decrement j.

```
class Solution {
    public boolean isPalindrome(String s) {
        s = s.toLowerCase();
        s = s.replaceAll("[^a-zA-Z0-9]", "");
        int n = s.length();
        int i = 0, j = n-1;
        while(i <= j || i < n || j > 0){
            if(s.charAt(i) != s.charAt(j)){
                return false;
            }
            i++;j--;
        }
        return true;
    }
}
```