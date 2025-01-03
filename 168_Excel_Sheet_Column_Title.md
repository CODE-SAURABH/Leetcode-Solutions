
# Optimize Method

```python
class Solution:
    def convertToTitle(self, columnNumber: int) -> str:
        result = []
        while columnNumber > 0:
            # Adjust for 1-based indexing; subtract 1 from columnNumber
            columnNumber -= 1
            # Get the current letter (remainder when divided by 26)
            result.append(chr(columnNumber % 26 + 65))  # 65 is ASCII for 'A'
            # Update columnNumber for the next iteration
            columnNumber //= 26
        
        # Reverse the result since we calculate from least significant to most significant
        return ''.join(reversed(result))

# Time  Complexity is O(n)
