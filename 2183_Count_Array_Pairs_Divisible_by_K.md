# BruteForce Method

```python
class Solution:
    def countPairs(self, nums: List[int], k: int) -> int:
        c=0
        for i in range(len(nums)):
            for j in range(i+1 ,len(nums)):
                if nums[i]*nums[j]%k==0 and i!=j:
                    c+=1
        return c

    Time complexity O(n*n)


# Optimize Method

```python
from collections import Counter
from math import gcd

class Solution:
    def countPairs(self, nums: List[int], k: int) -> int:
        freq = Counter()
        count = 0

        for num in nums:
            # Find the gcd of the current number with k
            gcd_num = gcd(num, k)
            
            # Check for pairs that can combine with gcd_num to make (a * b) % k == 0
            for gcd_key in freq:
                if (gcd_num * gcd_key) % k == 0:
                    count += freq[gcd_key]
            
            # Update the frequency of the current gcd
            freq[gcd_num] += 1
        
        return count
