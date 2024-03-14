### **Problem 2 : [Valid Anagram](https://leetcode.com/problems/valid-anagram/description/)**

**Algorithm 1:** 

1. Create 2 HashMap and Store the Frequency of Each Characther of Both the Strings Seperately.
2. Compare if the two HashMaps are Equal or Not.

```
class Solution {
    public boolean isAnagram(String s, String t) {
        HashMap<Character, Integer> hmap = new HashMap<>();
        HashMap<Character, Integer> hmap1 = new HashMap<>();

        for(char c : s.toCharArray()) hmap.put(c,hmap.getOrDefault(c,0)+1);
        for(char c : t.toCharArray()) hmap1.put(c,hmap1.getOrDefault(c,0)+1);

        return hmap.equals(hmap1);
    }
}
```

**Algorithm 2:** 

1. Covert The 2 Strings to 2 Different Character Arrays.
2. Sort the 2 Arrays.
3. Check if the Sorted Arrays are Equal or Not.

```
class Solution {
    public boolean isAnagram(String s, String t) {
        char[] arr = s.toCharArray();
        char[] arr1 = t.toCharArray();
        Arrays.sort(arr);
        Arrays.sort(arr1);

        return Arrays.equals(arr,arr1);
    }
}
```

**Algorithm 3:** 

1. Check if the Length of the 2 Strings are Equal or Not.
2. If Equal Move Forward else return False
3. Create a Array of Length 26 for each Character in the Alphabet.
4. Now Store the Frequency in it for the 1st String.
5. And for the 2nd String, Keep Decreasing the Freqency
6. If the Frequency Decreases than 0 then return false.
7. At the end of the loop return true.

```
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()) return false;

        int[] arr = new int[26];

        for(char a : s.toCharArray()) arr[a - 'a']++;
        for(char a : t.toCharArray()){
            if(arr[a-'a'] == 0) return false;
            arr[a-'a']--;
        }
        return true;
    }
}
```