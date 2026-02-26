# 628. Maximum Product of Three Numbers

## 🧠 Problem Summary
Given an integer array `nums`, return the maximum product of any three numbers.

---

## 💡 Intuition
The maximum product can be formed in two ways:
1. The three largest numbers in the array.
2. The two smallest (most negative) numbers and the largest number.

Because multiplying two negative numbers results in a positive value.

---

## ⚙️ Approach
1. Sort the array.
2. Compute:
   - Product of the last three elements.
   - Product of the first two elements and the last element.
3. Return the maximum of the two values.

---

## ⏱ Complexity
- Time: O(n log n)
- Space: O(1)

---

## 💻 Java Code
```java
import java.util.*;

class Solution {
    public int maximumProduct(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;
        int first = nums[n-1] * nums[n-2] * nums[n-3];
        int second = nums[0] * nums[1] * nums[n-1];
        return Math.max(first, second);
    }
}
```
