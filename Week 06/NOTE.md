学习笔记

## 产生式

* 用尖括号括起来的名称表示语法结构
* 语法结构分成基础结构和需要用其他语法结构定义的复合结构
    * 基础结构称终结符
    * 复合结构称非终结符
* 引号和中间的字符标识终结符
* 可以有括号
* 星号表示重复多次
* | 表示或
* + 标识至少一次

最小单元是终结符，通过一堆的终结符之间的组合关系形成结构（语法结构），最后形成一些非终结符。

具体例子看2.BNF文件（四则运算）

## 对象的基础知识

对象的三要素是
* 唯一标识
* 行为（改变对象的状态）
* 状态（描述对象）

对象其实是一个个单独个体。即使有两个个体它的行为和状态都一模一样，但是它们的唯一标识（内存地址）都是不一样的，是世界上独一无二的（非哲学的，只在编程领域内讨论）。

### 面向对象的具体思路

#### Object——Class（分类、归类）

分类、归类是类的两种主要流派

##### 归类

* 多继承，如c++

归类可以归属多个类，比如说鱼这一类又属于动物类，又属于水生动物类。（多继承）

##### 分类

* 单继承，有一个基类

只有一个从属关系，归为A类之后，就不可以归属别的类

#### Object——Prototype（原型）

任何对象仅仅需要描述它自己与原型的区别即可。跟分类的相同点就是只能有一个从属关系。

从属关系比较松散，比如说可以以水杯原型作为原型（小容量、承载液体）生成保温瓶原型（大容量、承载液体、保温）、生成脸盆原型（超大容量、承载液体）

### 抽象能力

这个我印象很深，当初老师提出这个作业我还没有头绪。看了答案后醍醐灌顶。

总体来说，就是看主谓宾。比如说，狗咬人。我们不是抽象狗、咬这个东西。而是重点在宾语，也就是例子中的人。

狗咬人、我打你。都是宾语对象的状态被改变了。所以我们重点关注都是抽象宾语对象的状态。再后来才是主语的行为。

例子：class Human {hurt(source, degree) {...}}

这样的话，就不管是猫咬人还是蛇咬人还是人打人，都可以hold的住了。

总结一下就是注意状态的改变。如果主语对象做出了某个行为，把自己的状态改变了的话。那主语对象也要做抽象。

比如说还是狗咬人，在具体的场景可能说狗咬了人，它的牙齿有血渍。状态被改变了，那么就需要做咬的抽象

### JS Object API

* {} / . / [] / Object.defineProperty 基本操作
* Object.create / Object.setPrototypeOf / Object.getPrototypeOf 基于原型的
* new / class / extends 基于分类的
* new / function / prototype 不推荐
