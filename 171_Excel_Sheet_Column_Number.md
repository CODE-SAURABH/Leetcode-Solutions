
# Optimize Method

```python

class Solution:
    def titleToNumber(self, columnTitle: str) -> int:
        columnNumber = 0
        for char in columnTitle:
            # Calculate the value of each character and add to columnNumber
            columnNumber = columnNumber * 26 + (ord(char) - ord('A') + 1)
        return columnNumber
Time Complexity ois O(n)
