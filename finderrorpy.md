# Practice
Set Mismatch
## 问题分析：
#### 
The set S originally contains numbers from 1 to n. But unfortunately, due to the data error, one of the numbers in the set got duplicated to another number in the set, which results in repetition of one number and loss of another number.
Given an array nums representing the data status of this set after the error. Your task is to firstly find the number occurs twice and then find the number that is missing. Return them in the form of an array.
## 编程实现：
```C++
class Solution(object):
    def findErrorNums(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        m = len(nums)
        dmap = [0] * m
        for n in nums:
            if not dmap[n - 1]: dmap[n - 1] = 1
            else:
    return [n, (1 + m) * m / 2 + n - sum(nums)]
```
## 总结体会：
有一个1-n的集合，之后数据出错导致一个数复制到另一个位置上，导致这个集合中有一个数出现了2次，有一个数出现了0次。采用的方法是利用了把数当作下标来使用，利用负数做标记的方法，分为出现一次，和出现0次的区分。