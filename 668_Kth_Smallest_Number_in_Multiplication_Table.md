# BruteForce Method

```python
class Solution:
    def findKthNumber(self, m: int, n: int, k: int) -> int:
        MT=[]
        for i in range(1, m + 1):
            for j in range(1, n + 1):
                MT.append(i*j)
        MT.sort()
        return MT[k-1]



```
