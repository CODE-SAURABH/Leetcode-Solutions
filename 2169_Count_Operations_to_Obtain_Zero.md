# BruteForce Method

```python
class Solution:
    def countOperations(self, num1: int, num2: int) -> int:
        if num1 ==0 or num2==0:
            return 0
        c=1
        while num1!=num2:
            c+=1
            if num1<num2:
                num2-=num1
            else:
                num1-=num2
        return c


# Optimize Method

```python

class Solution:
    def countOperations(self, num1: int, num2: int) -> int:
        c = 0
        while num1 != 0 and num2 != 0:
            if num1 // num2 > 0:
                c += num1 // num2
                num1 = num1 % num2
            elif num2 // num1 > 0:
                c += num2 // num1
                num2 = num2 % num1

        return c