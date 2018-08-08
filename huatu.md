# Practice
画出数码管显示时间
## 问题分析：
#### 
如何画出7段数码管并且显示出自己规定的时间?
## 说明：
要使用turtle绘图函数.
## 编程实现：
```C++
import turtle
def drawline(draw):##单段数码管
    turtle.pendown() if draw else turtle.penup()
    turtle.fd(40)
    turtle.right(90)
def drawdigit(digit):##多段数码管
    drawline(True) if digit in [2,3,4,5,6,8,9] else drawline(False)
    drawline(True) if digit in [0,1,3,4,5,6,7,8,9] else drawline(False)
    drawline(True) if digit in [0,2,3,5,6,8,9] else drawline(False)
    drawline(True) if digit in [0,2,6,8] else drawline(False)
    turtle.left(90)
    drawline(True) if digit in [0,4,5,6,8,9] else drawline(False)
    drawline(True) if digit in [0,2,3,5,6,7,8,9] else drawline(False)
    drawline(True) if digit in [0,1,2,3,4,7,8,9] else drawline(False)
    turtle.left(180)
    turtle.penup()
    turtle.fd(20)
def drawdate(date):
    for i in date:
        drawdigit(eval(i))
def main():
    turtle.setup(800,350,200,200)
    turtle.penup()
    turtle.fd(-300)
    turtle.pensize(10)
    drawdate('20180519')
    turtle.hideturtle()
    turtle.done()
main()
```
## 总结体会：
学习了绘图函数turtle后,发现还是比较有意思的,可以根据需求绘制出自己想要的图形.这里drawline进行绘画单短数码管,后面绘画多段数码管,然后对于不同的数字,因为是根据年月日来进行绘画的,所以最后会根据不同数码管选择不一样的数字,main函数中负责画[图](/home/caoliangjie/图片/2018-08-08 19-41-47屏幕截图.png) .最后画出来的就是我们想要的这个样子.要判断是否下笔需要看具体给的数字.