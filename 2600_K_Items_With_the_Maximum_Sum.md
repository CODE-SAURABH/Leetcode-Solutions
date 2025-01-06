
# Optimize Method

```python
class Solution:
    def kItemsWithMaximumSum(self, numOnes: int, numZeros: int, numNegOnes: int, k: int) -> int:
        res = 0
        if k <= numOnes:
            return k
        elif k > numOnes and k - numOnes <= numZeros:
            return numOnes
        elif k > numOnes and k - numOnes > numZeros:
            return numOnes - (k - numOnes - numZeros)