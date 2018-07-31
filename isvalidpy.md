# Practice
有效的括号
## 问题分析：
#### 
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。
有效字符串需满足：
  1.  左括号必须用相同类型的右括号闭合。
  2. 左括号必须以正确的顺序闭合。
##注意
空字符串可被认为是有效字符串。
## 编程实现：
```python
class Solution:
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        if s is None: return False  
        x = ['[','(','{']###存在list里
        y = ["]",")","}"]
        z = ["()","[]","{}"]      
        res = []
        for i in s:
            if i in x:
                res.append(i) 
            elif i in y:
                if res == []:
                    return False
                else:
                    temp = res.pop(-1) + i
                    if temp not in z:
                        return False
        if len(res) != 0:
            return False
        return True
```
## 总结体会：
开一个list，保证最后如果有相对应的匹配的括号，如果没有匹配的或者开头就遇到右边的括号就返回false，如果最后这一块能找到不匹配的括号，就返回false，有匹配直接返回true。