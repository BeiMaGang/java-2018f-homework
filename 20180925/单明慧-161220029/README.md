﻿# 18/11/5更新
+ 由于课上讲述了collection，因此使用collection对代码进行了一些更改。
所有类中，只有小喽啰的数量是随着阵型变化而动态变化的，因此对小喽啰使用容器ArrayList修改。
+ 将以前的一个文件划分为了不同的包和文件，使得结构更加清晰，更加易读。

# 结构说明
## 战场类（BattleField)
+ 砖块类(Tile)
     + 一个砖块上面可以站一个生物体。
+ 战场类(BattleField)
    + 战场类由 15 x 15 的砖块组成。
    + 战场类可以显示出自己的情况。

## 生物类(Creature)
+ 是所有参与战争生物体的基类。
+ 具有名字这个属性，以及tellName()这个方法。
+ 具有位于战场方位的x，y属性，以及改变自己位置的setPos()方法。
+ 葫芦娃，老爷爷，小喽啰，蛇精，蝎子精均继承了这个类。

## 编阵类(Form)
+ 分为葫芦娃一方和蛇精一方。
    + 葫芦娃一方只有长蛇阵，由formForGood()方法实现。
    + 蛇精一方会不断变换阵型，由FormForBad()实现。
+ 由于编阵需要对生物体的x，y属性进行操作，因此将各种生物体作为Form类的属性成员。

## 主函数
+ 流程为建立战场 -> 葫芦兄弟排序编队后进入战场 -> 反派编队后进入战场 -> 反派变换阵型。
***

# 存在的问题
+ 由于继承了Creature类， 葫芦娃不可以使用枚举类型（Java不支持多继承），是否存在方法既能继承Creature类又限制其取值范围？ 本程序于构造函数中做了限制，不知是否还有其它的方法可以解决。