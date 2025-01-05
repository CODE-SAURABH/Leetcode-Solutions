# BruteForce Method

```python
from itertools import permutations
class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        ans=[list(p) for p in permutations(nums)]
        res=[]
        for i in ans:
            if i not in res:
                res.append(i)
        return res



# Optimize Method

```python

class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        def backtrack(start):
            # Base case: if we've filled all positions, store the result
            if start == len(nums):
                result.append(nums[:])
                return
            
            seen = set()  # To track duplicates at the current level
            for i in range(start, len(nums)):
                if nums[i] in seen:
                    continue  # Skip if we've already tried this number at this level
                seen.add(nums[i])
                
                # Swap current element with the start index
                nums[start], nums[i] = nums[i], nums[start]
                
                # Recurse for the next index
                backtrack(start + 1)
                
                # Backtrack to restore the original order
                nums[start], nums[i] = nums[i], nums[start]
        
        nums.sort()  # Sort to handle duplicates more easily
        result = []
        backtrack(0)
        return result
