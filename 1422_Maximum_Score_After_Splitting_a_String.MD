# BruteForce Method

```python
class Solution:
    def maxScore(self, s: str) -> int:
        left=''
        right=''
        maxi=0
        for i in range(1,len(s)):
            left=s[:i]
            right=s[i:]
            lz=left.count('0')
            ro=right.count('1')
            sco=lz+ro
            maxi=max(maxi,sco)
        return maxi
        
Time Complexity O(n^2)
# Optimize Method

```python
class Solution:
    def maxScore(self, s: str) -> int:
        total_ones = s.count('1')
        left_zeros = 0
        max_score = 0

        for i in range(len(s) - 1):
            if s[i] == '0':
                left_zeros += 1
            else:
                total_ones -= 1

            score = left_zeros + total_ones
            max_score = max(max_score, score)

        return max_score

Time Complexity O(n)