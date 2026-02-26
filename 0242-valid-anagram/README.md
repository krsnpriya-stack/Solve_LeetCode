# 242. Valid Anagram

## 🧠 Problem Summary
Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, otherwise return `false`.

---

## 💡 Intuition
Two strings are anagrams if they contain the same characters in the same frequency.  
Sorting both strings allows us to compare them directly.

If the sorted versions are identical, the strings are anagrams.

---

## ⚙️ Approach
1. If the lengths are different, return `false`.
2. Convert both strings into character arrays.
3. Sort both arrays.
4. Compare the sorted arrays using `Arrays.equals()`.

---

## ⏱ Complexity
- Time: O(n log n)
- Space: O(n)

---

## 💻 Java Code
```java
import java.util.Arrays;

class Solution {
    public boolean isAnagram(String s, String t) {

        if (s.length() != t.length()) {
            return false;
        }

        char[] arr1 = s.toCharArray();
        char[] arr2 = t.toCharArray();

        Arrays.sort(arr1);
        Arrays.sort(arr2);

        return Arrays.equals(arr1, arr2);
    }
}
```
