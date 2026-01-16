# 217. Contains Duplicate

**LeetCode:** https://leetcode.com/problems/contains-duplicate/description/
**Date:** {2026-01-12}  
**Status:** ✅ Solved  
**Difficulty:** Easy  
**Tags/Pattern:** Hashing, Set  
**Time/Space:** O(n) / O(n)

---

## 1) Problem in 1 line

If there is a duplicate in the array return true else false
Explain the problem in one sentence.

---

## 2) My first thought (before coding)

creating a set and then looking if each element while traversing using a for loop is present in set or not

---

## 3) Mistakes / Confusions (Error Notebook 핵심)

- Mistake #1:
- Mistake #2:
- What I learned:

---

## 4) Final approach (in plain English)

create a set
write a for loop to traverse through a loop
now check if each element is in the set or not
if in set already return true
else return false
Steps of the solution like you’d explain to a friend.

---

## 5) Code (final)

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        numSet=set()
        for num in nums:
            if num not in numSet:
                numSet.add(num)
            else:
                return True
        return False
# paste final accepted code here
```
