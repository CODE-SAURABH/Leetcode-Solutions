# BruteForce Method

```python

class Solution:
    def kthDistinct(self, arr: List[str], k: int) -> str:
        f={}
        l=[]
        for i in arr:
            if i in f:
                f[i]+=1
            else:
                f[i]=1
        for key in f.keys():
            if f[key]==1:
                l.append(key)
        if k-1>=len(l):
            return ""
        return l[k-1]

Time Complexity O(n).

# Optimize Method

```python
from typing import List
from collections import Counter

class Solution:
    def kthDistinct(self, arr: List[str], k: int) -> str:
        # Count the frequency of each element in the array
        frequency = Counter(arr)
        
        # Iterate through the original array to maintain order
        for item in arr:
            if frequency[item] == 1:  # Check if the element is distinct
                k -= 1
                if k == 0:  # If k distinct elements are found, return the current element
                    return item
        
        # If fewer than k distinct elements are found
        return ""

Time Complexity O(n).