# BruteForce Method

```python
class Solution:
    def twoOutOfThree(self, nums1: List[int], nums2: List[int], nums3: List[int]) -> List[int]:
        ans = []
        for i in nums1:
            if (i in nums2 or i in nums3) and i not in ans: 
                ans.append(i)
        for i in nums2:
            if i in nums3 and i not in ans:
                ans.append(i)
        return ans
```

This solution has a time complexity of approximately \(O(n_1 \cdot n_2 + n_1 \cdot n_3 + n_2 \cdot n_3)\), where \(n_1\), \(n_2\), and \(n_3\) are the lengths of `nums1`, `nums2`, and `nums3` respectively.

---

# Optimize Method

```python
from typing import List

class Solution:
    def twoOutOfThree(self, nums1: List[int], nums2: List[int], nums3: List[int]) -> List[int]:
        # Convert lists to sets for faster membership checks
        set1, set2, set3 = set(nums1), set(nums2), set(nums3)
        
        # Find elements that appear in at least two sets
        result = (set1 & set2) | (set2 & set3) | (set3 & set1)
        
        return list(result)
```

This optimized solution reduces the time complexity to \(O(n_1 + n_2 + n3)\), where \(n_1\), \(n_2\), and \(n_3\) are the lengths of `nums1`, `nums2`, and `nums3`. It uses sets to leverage efficient intersection and union operations.