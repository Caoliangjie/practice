# Practice
Poor Pigs
## 问题分析：
#### 
There are 1000 buckets, one and only one of them contains poison, the rest are filled with water. They all look the same. If a pig drinks that poison it will die within 15 minutes. What is the minimum amount of pigs you need to figure out which bucket contains the poison within one hour.
Answer this question, and write an algorithm for the follow-up general case.
## 编程实现：
```C++
class Solution(object):
    def poorPigs(self, buckets, minutesToDie, minutesToTest):
        """
        :type buckets: int
        :type minutesToDie: int
        :type minutesToTest: int
        :rtype: int
        """
        times = minutesToTest / minutesToDie + 1    #每头猪最多可测试的水桶数
        num = 0
        while pow(times,num) < buckets:
            num = num + 1
        return num
```
## 总结体会：
每只猪在实验时间内可检测的数量是60/15+1=5（需要注意的是最后要+1，因为如果前面的水喝完都没死的话，说明毒水肯定是最后一桶，也不用再喝了）。
如果用两头小猪进行实验，则可将水桶定义为二维坐标，两头猪分别检测x与y方向的水：每头猪15分钟内需尝试5桶水（一排或一列）。 

