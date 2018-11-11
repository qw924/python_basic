### Approach: Last in First out, so Stack. 
```
class Solution:
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        stack = []
        for string in s:
            if string in "([{":
                stack.append(string)
            if string == ')':
                if not stack or stack.pop() != '(':
                    return False
            if string ==']':
                if not stack or stack.pop() != '[':
                    return False
            if string == '}':
                if not stack or stack.pop() != '{':
                    return False
        
        return not stack
```
### Complexity analysis
- Time complexity : O(n) because we simply traverse the given string one character at a time and push and pop operations on a stack take O(1)time.
- Space complexity : O(n) as we push all opening brackets onto the stack and in the worst case, we will end up pushing all the brackets onto the stack. e.g. ((((((((((.
