# 2517. Maximum Tastiness of Candy Basket

**LeetCode:** [https://leetcode.com/problems/maximum-tastiness-of-candy-basket/](https://leetcode.com/problems/maximum-tastiness-of-candy-basket/)
**Date:** 2026-02-06
**Status:** ✅ Solved
**Difficulty:** Medium
**Tags/Pattern:** Binary Search on Answer, Greedy, Sorting
**Time/Space:** O(n log R) / O(1)

---

## 1) Problem in 1 line

Pick `k` candies such that the **minimum price difference between any two chosen candies is maximized**.

---

## 2) My first thought (before coding)

I initially thought of checking all combinations, but that’s infeasible, so I realized this is a **maximize minimum** type problem, which hints at **binary search on the answer**.

---

## 3) Mistakes / Confusions (Error Notebook 핵심)

- Mistake #1: Tried thinking in terms of pairs instead of spacing between sorted prices.
- Mistake #2: Forgot that feasibility checking can be done greedily.
- What I learned: When asked to maximize a minimum value, try **binary search + greedy check**.

---

## 4) Final approach (in plain English)

- Sort the prices so differences are easy to reason about.
- Binary search on the minimum allowed tastiness value.
- For a guessed tastiness, greedily pick candies ensuring each is at least that far apart.
- If we can pick `k` candies, the tastiness is feasible, so try higher.
- Otherwise, reduce the search space.

---

## 5) Code (final)

```python
class Solution:
    def maximumTastiness(self, price: List[int], k: int) -> int:
        price.sort()
        low = 0
        high = max(price) - min(price)
        res = 0

        def check(mid):
            count = 1
            prev = price[0]
            for i in range(1, len(price)):
                if price[i] - prev >= mid:
                    count += 1
                    prev = price[i]
                if count == k:
                    return True
            return False

        while low <= high:
            mid = (low + high) // 2
            if check(mid):
                res = mid
                low = mid + 1
            else:
                high = mid - 1

        return res
```
