### Approach 1: Brute Force
The brute force approach is simple. Loop through each element xx and find if there is another value that equals to target - x
```
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in range(len(nums) - 1):
            for j in range(i+1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i,j]
```
### Complexity Analysis 1
- Time complexity : O(n^2) For each element, we try to find its complement by looping through the rest of array which takes O(n) time.   
n+(n-1)+(n-2)+...+1   
Therefore, the time complexity is O(n^2)
- Space complexity : O(1). 

### Approach 2: One-pass Hash Table
To improve our run time complexity, we need a more efficient way to check if the complement exists in the array. If the complement exists, we need to look up its index. What is the best way to maintain a mapping of each element in the array to its index? A hash table.
We reduce the look up time from O(n)O(n) to O(1)O(1) by trading space for speed. A hash table is built exactly for this purpose, it supports fast look up in near constant time.
It turns out we can do it in one-pass. While we iterate and inserting elements into the table, we also look back to check if current element's complement already exists in the table. If it exists, we have found a solution and return immediately.
```
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        idxDict = dict()
        for i, num in enumerate(nums):
            if target - num in idxDict:
                return [idxDict[target - num], i]
            idxDict[num] = i
```
### Complexity Analysis 2 
- Time complexity : O(n). We traverse the list containing nn elements only once. Each look up in the table costs only O(1) time.
- Space complexity : O(n). The extra space required depends on the number of items stored in the hash table, which stores at most nn elements.

