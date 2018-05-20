# Practice
判断路线成圈
## 问题分析：
#### 
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。
移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
## 编程实现：
```C++
class Solution {
public:
    bool judgeCircle(string moves) {
        int length=moves.length();
        char c;
        int x=0,y=0;
        for (int i= 0;i<length;++i) {
             c= moves.at(i);
            if (c=='U') {
                x++;
            } else 
                if (c=='D') {
                x--;
            } else 
                    if (c=='R') {
                y++;
            } else
                        if (c=='L') {
                y--;
            }
        }
        return x==0&&y==0;
    }
};

```
## 总结体会：
这里我们想象一下，既然是一系列的指令，我们就一步一步判断一下，毕竟这是一个二维的平面。x判断上下，y判断左右。U是上，上就x加（其实-1也一样，一个意思），D是向下，就减1，RL同理。如果x，y同时为0，说明走回远点，那就是走了圆，即为所得答案。