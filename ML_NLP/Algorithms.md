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


class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        res = defaultdict(list)
        for s in strs:
            count = [0] * 26
            for c in s:
                count[ord(c) - ord('a')] += 1
            #     print(f"{ord(c)} - {ord('a')} = {ord(c) - ord('a')}")
            # print(count)
            res[tuple(count)].append(s)
        #     print()
        # print(res)
        return list(res.values())
```

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        freq = [[] for i in range(len(nums)+1)]

        for i in nums:
            count[i] = 1 + count.get(i, 0)
        for num, cnt in count.items():
            freq[cnt].append(num)

        res = []
        for i in range(len(freq)-1, 0, -1):
            for i in freq[i]:
                res.append(i)
                if len(res) == k:
                    return res
```

 ```python
 class Solution:
    def encode(self, strs: List[str]) -> str:
        res = ""
        for i in strs:
            res += f"{len(i)}#{i}"
        return res
    def decode(self, s: str) -> List[str]:
        i = 0
        words = []
        while i < len(s):
            j = i
            while s[j] != "#":
                j += 1
            leng = int(s[i:j]) + 1
            words.append(s[j+1:j+leng])
            j += leng
            i = j
        return words



class Solution:

    def encode(self, strs: List[str]) -> str:
        res = ""
        for s in strs:
            res += str(len(s)) + "#" + s
        return res

    def decode(self, s: str) -> List[str]:
        res = []
        i = 0

        while i < len(s):
            j = i
            while s[j] != '#':
                j += 1
            length = int(s[i:j])
            i = j + 1
            j = i + length
            res.append(s[i:j])
            i = j

        return res

 ```