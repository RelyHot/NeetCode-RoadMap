### **Problem 4 : [Group Anagrams](https://leetcode.com/problems/group-anagrams/description/)**

**Algorithm:** 

1. Create a HashMap.
2. For Each String Create a Character Array for the Same
3. Sort The Character Array and Convert it to a String Again.
4. Check if HashMap has the Sorted String. if it DoesNot then Add it to the HashMap with an Empty ArrayList.
5. Add the Original String to The HashMap.
6. Return a New ArrayList of all the ArrayList from the HashMap Values.

```
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String,List<String>> hmap = new HashMap<>();
        for(String s : strs){
            char[] a = s.toCharArray();
            Arrays.sort(a);
            String s1 = new String(a);
            if(!hmap.containsKey(s1)) hmap.put(s1,new ArrayList<>());
            hmap.get(s1).add(s);
        }
        return new ArrayList<>(hmap.values());
    }
}
```