# Practice
只出现一次的数字
## 问题分析：
#### 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。
## 编程实现：
```C++
class Solution:
    def singleNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        tagdict={}
        for i in nums:##找是不是又存在的重复的数
            if i in tagdict:
                tagdict[i]+=1
            else:
                tagdict[i]=1
        taglist=[]
        for j in tagdict:
            if tagdict[j]==1:
                taglist.append(j)
        return taglist[0]#不能输出列表，因为最后要的是一个数。
```
## 总结体会：
基本的解释注释里也有写，这里还是用到了列表的操作，只要保证计数为1的元素有，然后最后输出即可。