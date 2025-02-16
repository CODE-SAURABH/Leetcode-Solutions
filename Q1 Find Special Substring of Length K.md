# Optimize Method

```python
class Solution:
    def hasSpecialSubstring(self, s: str, k: int) -> bool:
        if k <= 0:
            return False

        for i in range(len(s) - k + 1):
            substring = s[i:i + k]
            if len(set(substring)) == 1:
                if (i == 0 or s[i - 1] != substring[0]) and (i + k == len(s) or s[i + k] != substring[0]):
                    return True

        return False
```
