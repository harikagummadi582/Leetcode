# {ID}. {Title}

**LeetCode:** https://leetcode.com/problems/two-sum/submissions/1884537512/  
**Date:** {2026-01-13}  
**Status:** ✅ Solved
**Difficulty:** Easy  
**Tags/Pattern:** {Hashing, Set}  
**Time/Space:** O(n) / O(n)

---

## 1) Problem in 1 line

there is an array with numbers and i have to return indices of the numbers which sum up to target given as input
Explain the problem in one sentence.

---

## 2) My first thought (before coding)

i wanted to store the indexes of the numbers not in the map to check later if the difference of target and the current number being checked in the loop is in the map or not to return indexes.
What I tried first, and why.

---

## 3) Mistakes / Confusions (Error Notebook 핵심)

- Mistake #1:
- Mistake #2:
- What I learned:

---

## 4) Final approach (in plain English)

i created a hashmap
for loop to traverse through the loop and add each number with index to map like number:index format
search for difference in target-number in map to return its index
Steps of the solution like you’d explain to a friend.

---

## 5) Code (final)

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numMap={}
        for i, num in enumerate(nums):
            if target-num not in numMap:
                numMap[num]=i
            else:
                return [numMap[target-num], i]
# paste final accepted code here
```
