# Arrays & Hashing


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

```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * len(nums)
        prefix = 1
        for i in range(len(nums)):
            res[i] = prefix
            prefix *= nums[i]

        suffix = 1
        for i in range(len(nums) -1, -1, -1):
            res[i] *= suffix
            suffix *= nums[i]

        return res
```

```python
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        cols = collections.defaultdict(set)
        rows = collections.defaultdict(set)
        sqas = collections.defaultdict(set)

        for c in range(9):
            for r in range(9):
                if board[c][r] == ".":
                    continue

                if (board[c][r] in cols[c] or
                    board[c][r] in rows[r] or
                    board[c][r] in sqas[(c // 3, r // 3)]):
                    return False

                cols[c].add(board[c][r])
                rows[r].add(board[c][r])
                sqas[(c // 3, r // 3)].add(board[c][r])

        return True
```

```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        sn = sorted(set(nums))
        lgst = [1]
        cnt = 0

        for i in range(len(sn)-1):
            if sn[i] + 1 == sn[i+1]:
                lgst[cnt] += 1
            else:
                cnt += 1
                lgst.append(1)

        return max(lgst) if nums else 0


class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0

        for num in numSet:
            if (num - 1) not in numSet:
                length = 1
                while (num + length) in numSet:
                    length += 1
                longest = max(length, longest)
        return longest


class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        mp = defaultdict(int)
        res = 0

        for num in nums:
            if not mp[num]:
                mp[num] = mp[num - 1] + mp[num + 1] + 1
                mp[num - mp[num - 1]] = mp[num]
                mp[num + mp[num + 1]] = mp[num]
                res = max(res, mp[num])
        return res

```


# Two Pointers

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        st = [i.lower() for i in s if i.isalnum()]

        l, r = 0, len(st) - 1
        while l < r:
            if st[l] != st[r]:
                return False
            l += 1
            r -= 1
        return True
```

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1

        while l < r:
            if numbers[l] + numbers[r] > target:
                r -= 1
            elif numbers[l] + numbers[r] < target:
                l += 1
            else:
                return [l + 1, r + 1]
```

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        nums.sort()
        ln = len(nums) - 1
        out = []  

        for i in range(0, ln):
            l = i + 1
            r = ln
            while l < r:
                n = nums[l] + nums[r]
                if n > -nums[i]:
                    r -= 1
                elif n < -nums[i]:
                    l += 1
                else:
                    if [nums[i], nums[l], nums[r]] not in out:
                        out.append([nums[i], nums[l], nums[r]])
                    l += 1
        return out



class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()

        for i, a in enumerate(nums):
            if a > 0:
                break

            if i > 0 and a == nums[i - 1]:
                continue

            l, r = i + 1, len(nums) - 1
            while l < r:
                threeSum = a + nums[l] + nums[r]
                if threeSum > 0:
                    r -= 1
                elif threeSum < 0:
                    l += 1
                else:
                    res.append([a, nums[l], nums[r]])
                    l += 1
                    r -= 1
                    while nums[l] == nums[l - 1] and l < r:
                        l += 1

        return res
```

```python
class Solution:
    def maxArea(self, heights: List[int]) -> int:
class Solution:
    def maxArea(self, heights: List[int]) -> int:
        l, r, ma = 0, len(heights) - 1, 0
        while l < r:
            su = (r - l) * min(heights[r], heights[l])
            if su > ma:
                ma = su
            if heights[l] < heights[r]:
                l += 1
            else:
                r -= 1
        return ma


class Solution:
    def maxArea(self, heights: List[int]) -> int:
        l, r = 0, len(heights) - 1
        res = 0

        while l < r:
            area = min(heights[l], heights[r]) * (r - l)
            res = max(res, area)
            if heights[l] <= heights[r]:
                l += 1
            else:
                r -= 1
        return res

```

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        pre, post = [], []
        f, s = 0, 0
        water = 0
        for i in height:
            if i > f:
                f = i
            pre.append(f)
        for i in height[::-1]:
            if i > s:
                s = i
            post.insert(0, s)
        for i in range(0, len(height) - 1):
            water += min(pre[i], post[i]) - height[i]
        return water



class Solution:
    def trap(self, height: List[int]) -> int:
        n = len(height)
        if n == 0:
            return 0

        leftMax = [0] * n
        rightMax = [0] * n

        leftMax[0] = height[0]
        for i in range(1, n):
            leftMax[i] = max(leftMax[i - 1], height[i])

        rightMax[n - 1] = height[n - 1]
        for i in range(n - 2, -1, -1):
            rightMax[i] = max(rightMax[i + 1], height[i])

        res = 0
        for i in range(n):
            res += min(leftMax[i], rightMax[i]) - height[i]
        return res



class Solution:
    def trap(self, height: List[int]) -> int:
        if not height:
            return 0

        l, r = 0, len(height) - 1
        leftMax, rightMax = height[l], height[r]
        res = 0
        while l < r:
            if leftMax < rightMax:
                l += 1
                leftMax = max(leftMax, height[l])
                res += leftMax - height[l]
            else:
                r -= 1
                rightMax = max(rightMax, height[r])
                res += rightMax - height[r]
        return res

```


# Stack

```python
class Solution:
    def isValid(self, s: str) -> bool:
        st = []
        clt = {")": "(", "}": "{", "]": "["}
        for i in s:
            if i in clt:
                if st and clt[i] == st[-1]:
                    st.pop(-1)
                else:
                    return False
            else:
                st.append(i)
        return True if not st else False
```

```python
class MinStack:
    def __init__(self):
        self.arr = []
        self.prefix = []

    def push(self, val: int) -> None:
        if self.prefix and self.prefix[-1] < val:
            self.prefix.append(self.prefix[-1])
        else:
            self.prefix.append(val)
        self.arr.append(val)

    def pop(self) -> None:
        del self.arr[-1]
        del self.prefix[-1]

    def top(self) -> int:
        return self.arr[-1]

    def getMin(self) -> int:
        return self.prefix[-1]


    def push(self, val: int) -> None:
        self.stack.append(val)
        val = min(val, self.minStack[-1] if self.minStack else val)
        self.minStack.append(val)



class MinStack:
    def __init__(self):
        self.min = float('inf')
        self.stack = []

    def push(self, val: int) -> None:
        if not self.stack:
            self.stack.append(0)
            self.min = val
        else:
            self.stack.append(val - self.min)
            if val < self.min:
                self.min = val

    def pop(self) -> None:
        if not self.stack:
            return

        pop = self.stack.pop()

        if pop < 0:
            self.min = self.min - pop

    def top(self) -> int:
        top = self.stack[-1]
        if top > 0:
            return top + self.min
        else:
            return self.min

    def getMin(self) -> int:
        return self.min

```


```python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        rnp = []

        for i in range(0, len(tokens)):
            if tokens[i] in "+-/*":
                if tokens[i] == '+':
                    rnp.append(rnp[-2] + rnp[-1])
                    del rnp[-2]
                    del rnp[-2]

                elif tokens[i] == '*':
                    rnp.append(rnp[-2] * rnp[-1])
                    del rnp[-2]
                    del rnp[-2]

                elif tokens[i] == '-':
                    rnp.append(rnp[-2] - rnp[-1])
                    del rnp[-2]
                    del rnp[-2]

                elif tokens[i] == '/':
                    rnp.append(int(rnp[-2] / rnp[-1]))
                    del rnp[-2]
                    del rnp[-2]

            else:
                rnp.append(int(tokens[i]))
            print(rnp)
        return rnp[-1]



class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        stack = []
        for c in tokens:
            if c == "+":
                stack.append(stack.pop() + stack.pop())
            elif c == "-":
                a, b = stack.pop(), stack.pop()
                stack.append(b - a)
            elif c == "*":
                stack.append(stack.pop() * stack.pop())
            elif c == "/":
                a, b = stack.pop(), stack.pop()
                stack.append(int(float(b) / a))
            else:
                stack.append(int(c))
        return stack[0]

```

```python
class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        result = [0] * len(temperatures)
        stack = [] ## [index, tempe]

        for i, t in enumerate(temperatures):
            while stack and stack[-1][1] < t:
                index, tempe = stack.pop()
                result[index] = i - index
            stack.append([i, t])

        return result
```

```python
class Solution:
    def carFleet(self, target: int, position: List[int], speed: List[int]) -> int:
        ref = [[p, s] for p, s in zip(position, speed)]
        stack = []

        for p, s in sorted(ref)[::-1]:
            stack.append((target - p) / s)
            if len(stack) > 1 and stack[-2] >= stack[-1]:
                stack.pop()

        return len(stack)
```

# Binary search

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l <= r:
            mid = (r + l) // 2
            if target > nums[mid]:
                l = mid + 1
            elif target < nums[mid]:
                r = mid - 1
            else:
                return mid
        return -1


import bisect
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        index = bisect.bisect_left(nums, target)
        return index if index < len(nums) and nums[index] == target else -1

```

```python
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:

        for i in matrix:
	        if target < i[0] or target > i[-1]:
                continue
            l, r = 0, len(i) - 1
            while l <= r:
                mid = (l + r) // 2
                if i[mid] < target:
                    l = mid + 1
                elif i[mid] > target:
                    r = mid - 1
                elif i[mid] == target:
                    return True
        return False


class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        ROWS, COLS = len(matrix), len(matrix[0])

        l, r = 0, ROWS * COLS - 1
        while l <= r:
            m = l + (r - l) // 2
            row, col = m // COLS, m % COLS
            if target > matrix[row][col]:
                l = m + 1
            elif target < matrix[row][col]:
                r = m - 1
            else:
                return True
        return False

```

```python
class Solution:
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        l, r = 1, max(piles)
        res = r

        while l <= r:
            hours = 0
            k = (r + l) // 2
            for i in piles:
                hours += math.ceil(i / k)
            if hours <= h:
                res = min(res, k)
                r = k - 1
            else:
                l = k + 1

        return res
```

```python
class Solution:
    def findMin(self, nums: List[int]) -> int:
        l, r = 0, len(nums) - 1
        res = nums[0]
        while l <= r:
            if nums[l] < nums[r]:
                res = min(res, nums[l])
                break

            mid = (l + r) // 2
            res = min(res, nums[mid])
            if nums[mid] >= nums[l]:
                l = mid + 1
            else:
                r = mid - 1
        return res



class Solution:
    def findMin(self, nums: List[int]) -> int:
        l, r = 0, len(nums) - 1
        while l < r:
            m = l + (r - l) // 2
            if nums[m] < nums[r]:
                r = m
            else:
                l = m + 1
        return nums[l]

```


```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l <= r:
            mid = (l + r) // 2

            if nums[mid] == target:
                return mid
            if nums[mid] >= nums[l]:
                if target > nums[mid] or target < nums[l]:
                    l = mid + 1
                else:
                    r = mid - 1
            else:
                if target < nums[mid] or target > nums[r]:
                    r = mid - 1
                else:
                    l = mid + 1

        return -1
```

```python
class TimeMap:
    def __init__(self):
        self.base = []

    def set(self, key: str, value: str, timestamp: int) -> None:
        self.base.append([key, value, timestamp])

    def get(self, key: str, timestamp: int) -> str:
        for i in range(timestamp, -1, -1):
            for k in self.base:
                if k[0] == key and i == k[2]:
                    return k[1]

        return ""



```