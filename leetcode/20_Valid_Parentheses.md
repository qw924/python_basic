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
