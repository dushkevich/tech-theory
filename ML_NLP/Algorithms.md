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



class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        countS, countT = {}, {}
        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)
        return countS == countT
        

class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        return sorted(s) == sorted(t)

```

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        sol_map = {}
        for i in nums:
            diff = target - i
            if diff not in sol_map:
                sol_map[i] = nums.index(i)
            else:
                return [sol_map[diff], nums.index(i, sol_map[diff]+1)]




class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        indices = {}  # val -> index

        for i, n in enumerate(nums):
            indices[n] = i

        for i, n in enumerate(nums):
            diff = target - n
            if diff in indices and indices[diff] != i:
                return [i, indices[diff]]
        return []



class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {}  # val -> index

        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i

```

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        a, z, f = [], {}, []
        for i in strs:
            a.append(''.join(sorted(i)))
            z[''.join(sorted(i))] = []
        a.sort()
        for i in z.keys():
            for s in strs:
                if i == ''.join(sorted(s)):
                    z[i].append(s)
        for i in z.keys():
            f.append(z[i])
        return f



```