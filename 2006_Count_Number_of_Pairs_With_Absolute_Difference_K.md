# BruteForce Method 

class Solution:
    def countKDifference(self, nums: List[int], k: int) -> int:
        c=0
        for i in range(len(nums)-1):
            for j in range(i+1,len(nums)):
                if abs(nums[i]-nums[j])==k:
                    c+=1
        return c

This solution has a time complexity of O(n^2), where n is the length of the array.

# Optimize Method 

class Solution:
    def countKDifference(self, nums: List[int], k: int) -> int:
        count=0
        from collections import Counter
        mydict=Counter(nums)   
        for i in mydict:
            if i+k in mydict:
                count=count+ mydict[i]*mydict[i+k]  
        return count

This reduces the time complexity to O(n), where n is the length of the array.
