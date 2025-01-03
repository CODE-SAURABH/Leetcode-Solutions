# BruteForce Method

````python

class Solution:
    def countEven(self, num: int) -> int:
        def digitsum(n):
            sum=0
            while n!=0:
                rem=n%10
                n//=10
                sum+=rem
            return (sum%2==0)
        ans=0
        for i in range(2,num+1):
            if digitsum(i):
                ans+=1
        return ans



# Optimize Method

```python
class Solution:
    def countEven(self, num: int) -> int:
        def digit_sum(n):
            return sum(int(digit) for digit in str(n))
        
        count = 0
        for i in range(2, num + 1):
            if digit_sum(i) % 2 == 0:
                count += 1
        return count

