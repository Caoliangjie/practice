## 两数之和
### 
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。
###
```C++
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i, num in enumerate(nums):##同时把下标和元素一起遍历。
            num2 = target-num
            if num2 in nums:    # 对于这个数要是在nums里的话
                t = nums.index(num2) #查找第一个匹配的位置，省去了遍历所有的功夫。点背点就到最后一个。
                if t != i:
                    return [i, t]
```
## 总结
用了list的一些特有函数，比起c++而言python的list优势这时候体现出来了，把下标找出来之后只要第一个相等的返回即可。（如果遍历求解，会超时，因为python本身比c++运行时间就是慢）