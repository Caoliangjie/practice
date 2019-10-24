## 赎金信
'''
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        a = list(ransomNote)
        b = list(magazine)
        
        try:
            for i in a:
                b.remove(i)
            return True
        except:
            return False
'''
这里可以用一行代码就解决,采取的是字符匹配的解法。
'''
class Solution(object):
    def canConstruct(self, ransomNote, magazine):
        """
        :type ransomNote: str
        :type magazine: str
        :rtype: bool
        """
        return collections.Counter(magazine) & collections.Counter(ransomNote) == collections.Counter(ransomNote)
'''
