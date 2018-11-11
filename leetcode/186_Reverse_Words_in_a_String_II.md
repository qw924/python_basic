### Approach
1. First reverse every thing
from 'the sky is blue' to 'eulb si yks eht'
2. Second is to reverse every word
two pointers 
i for the letter before space
j for the letter after space
then use the first step reverse function  
revvers function needs begin and end
```
class Solution:
    def reverseWords(self, str):
        """
        :type str: List[str]
        :rtype: void Do not return anything, modify str in-place instead.
        """
        beg = 0
        for i in range(len(str)):
            if str[i] == ' ':
                self.reverse(str, beg, i-1)
                beg = i + 1
            elif i == len(str) -1:
                self.reverse(str, beg, i)
        self.reverse(str, 0, len(str)-1)#最后一步，整个大反转
    
    def reverse(self, s, start, end):
        while start < end:
            s[start], s[end] = s[end], s[start]
            start += 1
            end -= 1
```
