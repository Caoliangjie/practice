# Practice
4的幂
## 问题分析：
#### 
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。

## 示例:
当 num = 16 时 ，返回 true 。 当 num = 5时，返回 false。
## 编程实现：
```C++
        if num<=0:
            return False
        return True if pow(4,int(math.log(num,4)))==num else False
```
## 总结体会：
比较简洁的做法，就是不断的模四，毕竟是4的幂，如果最后能到1说明是4的幂，不是的话那么就返回false。