# 387. First Unique Character in a String

## 🧠 Problem Summary
Given a string `s`, return the index of the first non-repeating character.  
If no such character exists, return `-1`.

---

## 💡 Intuition
To determine the first unique character, we compare each character with every other character in the string.  
If no match is found for a character at index `i`, then it is unique.

---

## ⚙️ Approach
1. Iterate through the string using index `i`.
2. For each character, compare it with all other characters using another loop.
3. If a duplicate is found, mark it as not unique.
4. Return the index of the first character that remains unique.
5. If none exist, return `-1`.

---

## ⏱ Complexity
- Time: O(n²)
- Space: O(1)

---

## 💻 Java Code
```java
class Solution {
    public int firstUniqChar(String s) {

        for (int i = 0; i < s.length(); i++) {
            boolean isUnique = true;

            for (int j = 0; j < s.length(); j++) {
                if (i != j && s.charAt(i) == s.charAt(j)) {
                    isUnique = false;
                    break;
                }
            }

            if (isUnique) {
                return i;
            }
        }

        return -1;
    }
}
```
