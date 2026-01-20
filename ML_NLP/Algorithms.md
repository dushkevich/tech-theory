```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        ## return False if len(nums) == len(set(nums)) else True
        ## return len(set(nums)) < len(nums)
        hma = {}
        for i in nums:
            if i not in hma:
                hma[i] = 0
            hma[i] += 1
            if hma[i] > 1:
                return True
        return False
        

class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        for i in range(1, len(nums)):
            if nums[i] == nums[i - 1]:
                return True
        return False
```

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        ## return sorted(s) == sorted(t)
        fir, sec = {}, {}
        for i in s:
            if i not in fir:
                fir[i] = 0
            fir[i] += 1
        for i in t:
            if i not in fir.keys():
                return False
            if i not in sec:
                sec[i] = 0
            sec[i] += 1
        for i in s:
            if i not in sec.keys():
                return False
            if fir[i] != sec[i]:
                return False
        return True



```