# BruteForce Method

```python

class Solution:
    def arrangeCoins(self, n: int) -> int:
        if n==1:
            return 1
        for i in range(1,n+1):
            if n>=i:
                n-=i
            else:
                return i-1

Time Complexity:  𝑂(sqrt(𝑛))


# Optimize Method

```python

class Solution:
    def arrangeCoins(self, n: int) -> int:
        return floor(-0.5+sqrt(2*n+0.25))

Time Complexity: O(1)
